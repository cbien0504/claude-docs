---
title: Công cụ (Tools)
source: https://platform.claude.com/docs/en/managed-agents/tools
description: Cấu hình các công cụ có sẵn cho agent của bạn.
featureMetadata:
  topic:
    title: Managed Agents
    url: https://platform.claude.com/docs/en/managed-agents/overview
  status: beta
  betaHeader: managed-agents-2026-04-01
  zdr:
    eligibility: not-eligible
    note: Sessions are stateful resources; transcripts persist until you delete them. Applies to all Managed Agents sub-features, including Self-hosted sandboxes.
  supportedModels:
    - claude-fable-5-1
    - claude-mythos-5-1
    - claude-fable-5
    - claude-mythos-5
    - claude-mythos-preview
    - claude-opus-5-5
    - claude-opus-5
    - claude-sonnet-5-5
    - claude-sonnet-5
    - claude-haiku-5-5
    - claude-haiku-4-5-20251001
    - claude-opus-4-8
    - claude-opus-4-7
    - claude-opus-4-6
    - claude-sonnet-4-6
    - claude-opus-4-5-20251101
    - claude-sonnet-4-5-20250929
  supportedPlatforms:
    Claude API: beta
    Claude Platform on AWS: beta
---

> Đây là bản dịch không chính thức. Nội dung gốc thuộc về Anthropic, xem bản chính thức tại [platform.claude.com/docs](https://platform.claude.com/docs/en/managed-agents/tools). Khi có khác biệt, bản tiếng Anh là bản đúng.

Claude Managed Agents cung cấp một bộ công cụ dựng sẵn mà Claude có thể tự chủ sử dụng trong một [session](sessions.md). Bạn kiểm soát những công cụ nào khả dụng bằng cách chỉ định chúng trong cấu hình agent.

Claude Managed Agents cũng hỗ trợ các công cụ tùy chỉnh do người dùng định nghĩa. Ứng dụng của bạn chạy các công cụ này một cách riêng biệt và trả kết quả về cho Claude, Claude dùng kết quả đó để tiếp tục tác vụ. Để cung cấp cho agent các công cụ từ một MCP server, hãy dùng [MCP connector](mcp-connector.md).

## Các công cụ khả dụng

Bộ công cụ của agent (agent toolset) bao gồm các công cụ sau. Tất cả đều được bật theo mặc định khi bạn đưa toolset vào cấu hình agent.

| Công cụ    | Tên          | Mô tả                                                           |
| ---------- | ------------ | --------------------------------------------------------------- |
| Bash       | `bash`       | Chạy các lệnh bash trong một shell session                      |
| Read       | `read`       | Đọc một file từ hệ thống file của sandbox                       |
| Write      | `write`      | Ghi một file vào hệ thống file của sandbox                      |
| Edit       | `edit`       | Thực hiện thay thế chuỗi trong một file                         |
| Glob       | `glob`       | Thực hiện khớp mẫu file nhanh bằng các mẫu glob                 |
| Grep       | `grep`       | Tìm kiếm văn bản bằng các mẫu regex                             |
| Web fetch  | `web_fetch`  | Lấy nội dung từ một URL                                         |
| Web search | `web_search` | Tìm kiếm thông tin trên web                                     |

Khi đầu ra của một công cụ vượt quá 100.000 ký tự (khoảng 25.000 token), nó sẽ tự động được ghi vào một file trong [sandbox](environments.md). Mô hình nhận được bản xem trước đã cắt ngắn kèm đường dẫn file và có thể đọc toàn bộ nội dung từ đó.

## Cấu hình toolset

Bật toàn bộ toolset bằng `agent_toolset_20260401` khi tạo một agent. Dùng mảng `configs` (csharp, go: `Configs`) để tắt các công cụ cụ thể hoặc ghi đè cài đặt của chúng. Mỗi mục được xác định bằng `name` (csharp, go: `Name`), nhận một giá trị từ cột Tên trong [Các công cụ khả dụng](tools.md#available-tools). Mỗi mục cũng chấp nhận một trường `type` (csharp, go: `Type`) tùy chọn với cùng giá trị.

Mỗi mục cấu hình cũng có thể đặt `permission_policy` (java, php: `permissionPolicy`; csharp, go: `PermissionPolicy`). Chính sách này kiểm soát việc các lệnh gọi của công cụ chạy mà không cần xác nhận, yêu cầu xác nhận, hay được máy chủ đánh giá riêng từng lệnh gọi. Xem [Permission policies](permission-policies.md) để biết các loại chính sách khả dụng.

Ví dụ sau bật toolset và tắt `web_fetch`:

### cURL

```bash
curl -fsSL https://api.anthropic.com/v1/agents \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "anthropic-version: 2026-10-21" \
  -H "anthropic-beta: managed-agents-2026-04-01" \
  -H "content-type: application/json" \
  -d '{
    "name": "Coding Assistant",
    "model": "claude-opus-5-5",
    "tools": [
      {
        "type": "agent_toolset_20260401",
        "configs": [
          {"name": "web_fetch", "enabled": false}
        ]
      }
    ]
  }'
```

### CLI

```bash
ant apply agent.md
```

File `agent.md`:

```markdown
---
name: Coding Assistant
model: claude-opus-5-5
tools:
  - type: agent_toolset_20260401
    configs:
      - name: web_fetch
        enabled: false
---
```

### Python

```python
agent = client.beta.agents.create(
    name="Coding Assistant",
    model="claude-opus-5-5",
    tools=[
        {
            "type": "agent_toolset_20260401",
            "configs": [
                {"name": "web_fetch", "enabled": False},
            ],
        },
    ],
)
```

### TypeScript

```typescript
const agent = await client.beta.agents.create({
  name: "Coding Assistant",
  model: "claude-opus-5-5",
  tools: [
    {
      type: "agent_toolset_20260401",
      configs: [{ name: "web_fetch", enabled: false }]
    }
  ]
});
```

### C#

```csharp
using Anthropic.Models.Beta.Agents;

var agent = await client.Beta.Agents.Create(new()
{
    Name = "Coding Assistant",
    Model = BetaManagedAgentsModel.ClaudeOpus5_5,
    Tools =
    [
        new BetaManagedAgentsAgentToolset20260401Params
        {
            Configs =
            [
                new BetaManagedAgentsWebFetchToolConfigParams { Enabled = false },
            ],
        },
    ],
});
```

### Go

```go
agent, err := client.Beta.Agents.New(ctx, anthropic.BetaAgentNewParams{
	Name: "Coding Assistant",
	Model: anthropic.BetaManagedAgentsModelConfigParams{
		ID: anthropic.BetaManagedAgentsModelClaudeOpus5_5,
	},
	Tools: []anthropic.BetaAgentNewParamsToolUnion{{
		OfAgentToolset20260401: &anthropic.BetaManagedAgentsAgentToolset20260401Params{
			Configs: []anthropic.BetaManagedAgentsAgentToolConfigParamsUnion{{
				OfWebFetch: &anthropic.BetaManagedAgentsWebFetchToolConfigParams{
					Enabled: anthropic.Bool(false),
				},
			}},
		},
	}},
})
if err != nil {
	panic(err)
}
```

### Java

```java
import com.anthropic.models.beta.agents.*;

var agent = client.beta().agents().create(AgentCreateParams.builder()
    .name("Coding Assistant")
    .model(BetaManagedAgentsModel.CLAUDE_OPUS_5_5)
    .addTool(BetaManagedAgentsAgentToolset20260401Params.builder()
        .addConfig(BetaManagedAgentsWebFetchToolConfigParams.builder()
            .enabled(false)
            .build())
        .build())
    .build());
```

### PHP

```php
use Anthropic\Beta\Agents\BetaManagedAgentsAgentToolset20260401Params;
use Anthropic\Beta\Agents\BetaManagedAgentsModel;
use Anthropic\Beta\Agents\BetaManagedAgentsWebFetchToolConfigParams;

$agent = $client->beta->agents->create(
    name: 'Coding Assistant',
    model: BetaManagedAgentsModel::CLAUDE_OPUS_5_5,
    tools: [
        BetaManagedAgentsAgentToolset20260401Params::with(
            configs: [
                BetaManagedAgentsWebFetchToolConfigParams::with(enabled: false),
            ],
        ),
    ],
);
```

### Ruby

```ruby
agent = client.beta.agents.create(
  name: "Coding Assistant",
  model: Anthropic::Beta::BetaManagedAgentsModel::CLAUDE_OPUS_5_5,
  tools: [
    {
      type: :agent_toolset_20260401,
      configs: [
        {name: :web_fetch, enabled: false}
      ]
    }
  ]
)
```

### Tắt các công cụ cụ thể

Để tắt một công cụ, đặt `enabled: false` trong mục `configs` của nó:

```json
{
  "type": "agent_toolset_20260401",
  "configs": [
    { "name": "web_fetch", "enabled": false },
    { "name": "web_search", "enabled": false }
  ]
}
```

### Chỉ bật các công cụ cụ thể

Đối tượng `default_config` đặt đường cơ sở cho mọi công cụ trong bộ, và các mục `configs` theo từng công cụ sẽ ghi đè nó. Để bắt đầu với mọi thứ ở trạng thái tắt và chỉ bật những gì bạn cần, hãy đặt `default_config.enabled` thành `false`:

```json
{
  "type": "agent_toolset_20260401",
  "default_config": { "enabled": false },
  "configs": [
    { "name": "bash", "enabled": true },
    { "name": "read", "enabled": true },
    { "name": "write", "enabled": true }
  ]
}
```

### Giới hạn web search và web fetch

Các mục `web_search` và `web_fetch` cũng chấp nhận danh sách domain, giới hạn lượng nội dung được tải về và vị trí tìm kiếm. Xem [Giới hạn các domain của web search và web fetch](tools-web-restrictions.md).

### Các kiểu mục cấu hình trong SDK

SDK định kiểu cho từng mục `configs` (csharp, go: `Configs`) theo công cụ. Kiểu này là một union với một thành viên cho mỗi công cụ dựng sẵn, được phân biệt bằng `type` (csharp, go: `Type`).

Trong Go, Java, C# và PHP, bạn xây dựng các mục từ các giá trị có kiểu thay vì từ dictionary hoặc hash thuần. Trong các SDK đó, kiểu phần tử của `configs` (csharp, go: `Configs`) chính là union, vì vậy hãy xây dựng mỗi mục từ kiểu thành viên tương ứng của từng công cụ.

Bạn có thể bỏ qua `type` (csharp, go: `Type`) khi xây dựng một mục, vì máy chủ suy ra nó từ `name` (csharp, go: `Name`). Phản hồi luôn bao gồm trường này. Việc định kiểu này không làm thay đổi JSON mà một mục được tuần tự hóa thành. Một request có các mục chỉ đặt `name`, `enabled` và `permission_policy` là hợp lệ dù có hay không có `type`.

## Công cụ tùy chỉnh

Công cụ tùy chỉnh tương tự như [công cụ phía client do người dùng định nghĩa](../agents-and-tools/tool-use/how-tool-use-works.md#user-defined-tools-client-executed) trong Messages API. Bạn chỉ định những thao tác nào khả dụng và chúng trả về gì, còn Claude quyết định khi nào và gọi chúng như thế nào.

Claude không tự chạy công cụ tùy chỉnh. Nó phát ra một request có cấu trúc, code của bạn chạy thao tác, và bạn trả kết quả về cho session.

Ví dụ sau tạo một agent với một công cụ tùy chỉnh, `get_weather`, và không có công cụ dựng sẵn nào:

### cURL

```bash
curl -fsSL https://api.anthropic.com/v1/agents \
  -H "x-api-key: $ANTHROPIC_API_KEY" \
  -H "anthropic-version: 2026-10-21" \
  -H "anthropic-beta: managed-agents-2026-04-01" \
  -H "content-type: application/json" \
  -d '{
    "name": "Weather Agent",
    "model": "claude-opus-5-5",
    "tools": [
      {
        "type": "custom",
        "name": "get_weather",
        "description": "Get current weather for a location",
        "input_schema": {
          "type": "object",
          "properties": {
            "location": {"type": "string", "description": "City name"}
          },
          "required": ["location"]
        }
      }
    ]
  }'
```

### CLI

```bash
ant apply agent.md
```

File `agent.md`:

```markdown
---
name: Weather Agent
model: claude-opus-5-5
tools:
  - type: custom
    name: get_weather
    description: Get current weather for a location
    input_schema:
      type: object
      properties:
        location:
          type: string
          description: City name
      required:
        - location
---
```

### Python

```python
agent = client.beta.agents.create(
    name="Weather Agent",
    model="claude-opus-5-5",
    tools=[
        {
            "type": "custom",
            "name": "get_weather",
            "description": "Get current weather for a location",
            "input_schema": {
                "type": "object",
                "properties": {
                    "location": {"type": "string", "description": "City name"},
                },
                "required": ["location"],
            },
        },
    ],
)
```

### TypeScript

```typescript
const agent = await client.beta.agents.create({
  name: "Weather Agent",
  model: "claude-opus-5-5",
  tools: [
    {
      type: "custom",
      name: "get_weather",
      description: "Get current weather for a location",
      input_schema: {
        type: "object",
        properties: { location: { type: "string", description: "City name" } },
        required: ["location"]
      }
    }
  ]
});
```

### C#

```csharp
using System.Text.Json;
using Anthropic.Models.Beta.Agents;

var agent = await client.Beta.Agents.Create(new()
{
    Name = "Weather Agent",
    Model = BetaManagedAgentsModel.ClaudeOpus5_5,
    Tools =
    [
        new BetaManagedAgentsCustomToolParams
        {
            Name = "get_weather",
            Description = "Get current weather for a location",
            InputSchema = new()
            {
                Properties = new Dictionary<string, JsonElement>
                {
                    ["location"] = JsonSerializer.SerializeToElement(
                        new { type = "string", description = "City name" }
                    ),
                },
                Required = ["location"],
            },
        },
    ],
});
```

### Go

```go
agent, err := client.Beta.Agents.New(ctx, anthropic.BetaAgentNewParams{
	Name: "Weather Agent",
	Model: anthropic.BetaManagedAgentsModelConfigParams{
		ID: anthropic.BetaManagedAgentsModelClaudeOpus5_5,
	},
	Tools: []anthropic.BetaAgentNewParamsToolUnion{{
		OfCustom: &anthropic.BetaManagedAgentsCustomToolParams{
			Name:        "get_weather",
			Description: "Get current weather for a location",
			InputSchema: anthropic.BetaManagedAgentsCustomToolInputSchemaParam{
				Properties: map[string]any{
					"location": map[string]any{
						"type":        "string",
						"description": "City name",
					},
				},
				Required: []string{"location"},
			},
		},
	}},
})
if err != nil {
	panic(err)
}
```

### Java

```java
import com.anthropic.models.beta.agents.*;
import java.util.Map;

var agent = client.beta().agents().create(AgentCreateParams.builder()
    .name("Weather Agent")
    .model(BetaManagedAgentsModel.CLAUDE_OPUS_5_5)
    .addTool(BetaManagedAgentsCustomToolParams.builder()
        .name("get_weather")
        .description("Get current weather for a location")
        .inputSchema(BetaManagedAgentsCustomToolInputSchema.builder()
            .properties(BetaManagedAgentsCustomToolInputSchema.Properties.builder()
                .putAdditionalProperty("location", JsonValue.from(Map.of(
                    "type", "string",
                    "description", "City name")))
                .build())
            .addRequired("location")
            .build())
        .build())
    .build());
```

### PHP

```php
use Anthropic\Beta\Agents\BetaManagedAgentsCustomToolInputSchema;
use Anthropic\Beta\Agents\BetaManagedAgentsCustomToolParams;
use Anthropic\Beta\Agents\BetaManagedAgentsModel;

$agent = $client->beta->agents->create(
    name: 'Weather Agent',
    model: BetaManagedAgentsModel::CLAUDE_OPUS_5_5,
    tools: [
        BetaManagedAgentsCustomToolParams::with(
            name: 'get_weather',
            description: 'Get current weather for a location',
            inputSchema: BetaManagedAgentsCustomToolInputSchema::with(
                properties: ['location' => ['type' => 'string', 'description' => 'City name']],
                required: ['location'],
            ),
        ),
    ],
);
```

### Ruby

```ruby
agent = client.beta.agents.create(
  name: "Weather Agent",
  model: Anthropic::Beta::BetaManagedAgentsModel::CLAUDE_OPUS_5_5,
  tools: [
    {
      type: :custom,
      name: "get_weather",
      description: "Get current weather for a location",
      input_schema: {
        type: :object,
        properties: {location: {type: "string", description: "City name"}},
        required: ["location"]
      }
    }
  ]
)
```

Tên của một công cụ tùy chỉnh không được bắt đầu bằng `mcp__` hoặc `ant__`, và không được trùng với tên của một công cụ agent dựng sẵn. Một request vi phạm quy tắc này sẽ trả về lỗi 400. Một agent đã có công cụ tùy chỉnh có tên bắt đầu bằng `ant__` chỉ chấp nhận bản cập nhật nếu bản cập nhật gửi `tools` (csharp, go: `Tools`) mà không có tên đó, vì vậy hãy đổi tên hoặc xóa công cụ trong lần cập nhật tiếp theo. Một session mới sẽ bị từ chối với lỗi 400 nếu có công cụ như vậy trên agent của nó (sau mọi [ghi đè](sessions.md#override-agent-configuration-for-a-session)), trên một agent trong danh sách `predefined_agents` (java, php: `predefinedAgents`; csharp, go: `PredefinedAgents`) của `subagents` (csharp, go: `Subagents`), hoặc trên một agent trong danh sách `predefined_agents` (java, php: `predefinedAgents`; csharp, go: `PredefinedAgents`) của `workflows` (csharp, go: `Workflows`). Các session đã tồn tại không bị ảnh hưởng.

Agent gọi các công cụ tùy chỉnh của nó trong một session. Để nhận các lệnh gọi và trả kết quả, xem [Trả lời các lệnh gọi công cụ làm tạm dừng session](events-and-streaming.md#handling-custom-tool-calls).

Đối với các session chạy trong một sandbox tự lưu trữ, environment worker có thể [phục vụ các công cụ tùy chỉnh từ sandbox](self-hosted-sandboxes-custom-tools.md). Chúng có thể bao gồm các công cụ bao bọc một MCP server bên trong mạng của bạn.

### Các phương pháp hay nhất cho định nghĩa công cụ tùy chỉnh

* **Cung cấp mô tả cực kỳ chi tiết.** Đây là yếu tố quan trọng nhất đối với hiệu suất của công cụ. Bạn cung cấp càng nhiều ngữ cảnh về các công cụ cho Claude, Claude càng xác định tốt khi nào và làm thế nào để dùng chúng. Hãy nhắm tới ba đến bốn câu cho mỗi mô tả công cụ, nhiều hơn nếu công cụ phức tạp. Mô tả của bạn nên bao gồm:

  * Công cụ làm gì
  * Khi nào nên dùng và khi nào không nên dùng
  * Mỗi tham số có ý nghĩa gì và ảnh hưởng ra sao đến hành vi của công cụ
  * Mọi lưu ý hoặc hạn chế quan trọng

* **Gộp các thao tác liên quan vào ít công cụ hơn.** Nhóm các hành động như `create_pr`, `review_pr` và `merge_pr` vào một công cụ duy nhất với tham số `action`. Ít công cụ hơn nhưng mạnh hơn sẽ giảm sự mơ hồ khi chọn công cụ và giúp Claude dễ điều hướng bề mặt công cụ của bạn hơn.

* **Dùng namespace có ý nghĩa trong tên công cụ.** Khi các công cụ của bạn trải rộng nhiều dịch vụ hoặc tài nguyên, hãy thêm tiền tố tên bằng tài nguyên (ví dụ `db_query` hoặc `storage_read`). Điều này giúp việc chọn công cụ rõ ràng khi thư viện của bạn lớn dần.

* **Thiết kế phản hồi của công cụ chỉ trả về thông tin có giá trị cao.** Trả về các định danh có ngữ nghĩa và ổn định (ví dụ slug hoặc UUID) thay vì các tham chiếu nội bộ khó hiểu. Chỉ đưa vào những trường mà Claude cần để xác định bước tiếp theo. Các phản hồi cồng kềnh lãng phí ngữ cảnh và khiến Claude khó trích xuất những gì quan trọng hơn.

## Các bước tiếp theo

- **[Giới hạn các domain của web search và web fetch](tools-web-restrictions.md):** Kiểm soát những trang mà công cụ web có thể truy cập, giới hạn nội dung được tải về và bản địa hóa kết quả tìm kiếm.
- **[MCP connector](mcp-connector.md):** Kết nối các MCP server với agent của bạn để truy cập các công cụ và nguồn dữ liệu bên ngoài.
- **[Permission policies](permission-policies.md):** Kiểm soát khi nào các công cụ của agent và MCP được chạy.
- **[Session event stream](events-and-streaming.md):** Gửi sự kiện, stream phản hồi, và ngắt hoặc chuyển hướng session trong khi nó đang chạy.

## Tính khả dụng

Agent toolset đang ở giai đoạn beta trên mọi mô hình.

### Hỗ trợ API

#### [Managed Agents](overview.md)

* Tính khả dụng: Có sẵn

| Trạng thái | Nền tảng đám mây                                                                          |
| ---------- | ----------------------------------------------------------------------------------------- |
| Beta       | Claude API, [Claude Platform on AWS](../build-with-claude/claude-platform-on-aws.md)      |

### Beta header bắt buộc

[Tổng quan về beta header](../api/beta-headers.md)

Beta header cho phép bạn truy cập các tính năng thử nghiệm và khả năng mô hình mới trước khi chúng trở thành một phần của API tiêu chuẩn.

* `managed-agents-2026-04-01`

### Xử lý dữ liệu

[Tổng quan về xử lý dữ liệu](../manage-claude/api-and-data-retention.md#feature-eligibility)

| Mục        | Zero data retention                                                                                                                                                    | HIPAA                                                                                 |
| ---------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Trạng thái | Không đủ điều kiện                                                                                                                                                     | Không đủ điều kiện                                                                    |
| Chi tiết   | Session là các tài nguyên có trạng thái; bản ghi (transcript) được lưu giữ cho đến khi bạn xóa chúng. Áp dụng cho tất cả tính năng con của Managed Agents, bao gồm Self-hosted sandboxes. | Áp dụng cho tất cả tính năng con của Managed Agents, bao gồm Self-hosted sandboxes.   |

Các endpoint áp dụng:

* `/v1/agents`
* `/v1/sessions`
* `/v1/environments`
