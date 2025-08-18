# Reference

## Agents

<details><summary><code>client.agents.<a href="/src/api/resources/agents/client/Client.ts">listAgents</a>({ ...params }) -> Sonyk.AgentListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all agents for the organization

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.agents.listAgents();
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Sonyk.ListAgentsRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Agents.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="/src/api/resources/agents/client/Client.ts">createAgent</a>({ ...params }) -> Sonyk.AgentResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new AI voice agent with specified configuration

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.agents.createAgent({
    agent_name: "Restaurant Receptionist",
    agent_json: {
        llm: {
            provider: "openai",
            model: "gpt-5",
            systemPrompt:
                "# Role\nYou are Georgia, a friendly and professional receptionist at the  restaurant.\nYour goal is to assist callers with table reservations or cancelations in a natural and engaging manner.\n\nRestaurant opening hours: 10 AM to 11 PM daily\nLocation: 24 Park Street\n\n# Tasks\n- Answer questions about the restaurant\n- Make table reservations\n- Cancel existing reservations\n- Provide information about menu and hours\n\n# Guidelines\n- Always be polite and professional\n- Confirm all reservation details\n- If you can't help, politely explain and offer alternatives\n",
        },
        stt: {
            provider: "deepgram",
            model: "nova-3",
            language: "en",
        },
        tts: {
            provider: "elevenlabs",
            model: "eleven_multilingual_v2",
            voiceId: "sarah",
        },
        name: "Georgia - Restaurant Receptionist",
        firstMessage: "Hello! Welcome to  restaurant. I'm Georgia, how can I help you today?",
    },
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Sonyk.CreateAgentRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Agents.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="/src/api/resources/agents/client/Client.ts">getAgent</a>(agentId) -> Sonyk.AgentDetailedResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific agent by ID with full configuration

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.agents.getAgent("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string` — Agent identifier

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Agents.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="/src/api/resources/agents/client/Client.ts">updateAgent</a>(agentId, { ...params }) -> Sonyk.AgentResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update agent configuration. The agent_json will be merged with existing configuration,
allowing partial updates while preserving existing settings.

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.agents.updateAgent("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.UpdateAgentRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Agents.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="/src/api/resources/agents/client/Client.ts">deleteAgent</a>(agentId) -> Sonyk.SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete an agent (permanent deletion)

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.agents.deleteAgent("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Agents.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="/src/api/resources/agents/client/Client.ts">getAgentTools</a>(agentId) -> Sonyk.ToolListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all tools assigned to a specific agent

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.agents.getAgentTools("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Agents.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="/src/api/resources/agents/client/Client.ts">assignToolToAgent</a>(agentId, { ...params }) -> Sonyk.SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Assign an existing tool to an agent

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.agents.assignToolToAgent("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", {
    toolId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.AssignToolToAgentRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Agents.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.agents.<a href="/src/api/resources/agents/client/Client.ts">unassignToolFromAgent</a>(agentId, { ...params }) -> Sonyk.SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Remove a tool assignment from an agent

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.agents.unassignToolFromAgent("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", {
    toolId: "toolId",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.UnassignToolFromAgentRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Agents.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

## Phones

<details><summary><code>client.phones.<a href="/src/api/resources/phones/client/Client.ts">listPhones</a>({ ...params }) -> Sonyk.PhoneListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all phone numbers for the organization

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.phones.listPhones({
    provider: "twilio",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Sonyk.ListPhonesRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Phones.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="/src/api/resources/phones/client/Client.ts">createPhone</a>({ ...params }) -> Sonyk.PhoneResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Add a new phone number to the organization

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.phones.createPhone({
    phoneNumber: "+xxxxxxxxxx",
    provider: "twilio",
    twilioSid: "ACxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    twilioToken: "xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Sonyk.CreatePhoneRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Phones.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="/src/api/resources/phones/client/Client.ts">getPhone</a>(phoneId) -> Sonyk.PhoneResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific phone by ID

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.phones.getPhone("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phoneId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Phones.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="/src/api/resources/phones/client/Client.ts">updatePhone</a>(phoneId, { ...params }) -> Sonyk.PhoneResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update phone details or agent assignment

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.phones.updatePhone("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phoneId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.UpdatePhoneRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Phones.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="/src/api/resources/phones/client/Client.ts">deletePhone</a>(phoneId) -> Sonyk.SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Deactivate a phone number

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.phones.deletePhone("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phoneId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Phones.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="/src/api/resources/phones/client/Client.ts">mapPhoneToAgent</a>(phoneId, { ...params }) -> Sonyk.PhoneResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Assign a phone number to a specific agent

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.phones.mapPhoneToAgent("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", {
    agentId: "agentId",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phoneId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.MapPhoneToAgentRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Phones.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.phones.<a href="/src/api/resources/phones/client/Client.ts">unmapPhoneFromAgent</a>(phoneId) -> Sonyk.PhoneResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Remove agent assignment from a phone number

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.phones.unmapPhoneFromAgent("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**phoneId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Phones.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

## Tools

<details><summary><code>client.tools.<a href="/src/api/resources/tools/client/Client.ts">listTools</a>({ ...params }) -> Sonyk.ToolListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all available tools for the organization

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.tools.listTools();
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Sonyk.ListToolsRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Tools.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.tools.<a href="/src/api/resources/tools/client/Client.ts">createTool</a>({ ...params }) -> Sonyk.ToolResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new tool/function that can be assigned to agents

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.tools.createTool({
    tool_name: "make_reservation",
    tool_description:
        "Creates a new restaurant reservation with the specified date, time, party size, and customer details",
    server_url: "https://api.restaurant.com/reservations",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Sonyk.CreateToolRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Tools.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.tools.<a href="/src/api/resources/tools/client/Client.ts">getTool</a>(toolId) -> Sonyk.ToolResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve a specific tool by ID

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.tools.getTool("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**toolId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Tools.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.tools.<a href="/src/api/resources/tools/client/Client.ts">updateTool</a>(toolId, { ...params }) -> Sonyk.ToolResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update tool configuration

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.tools.updateTool("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", {
    tool_name: "make_reservation",
    tool_description:
        "Creates a new restaurant reservation with the specified date, time, party size, and customer details",
    server_url: "https://api.restaurant.com/reservations",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**toolId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.CreateToolRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Tools.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.tools.<a href="/src/api/resources/tools/client/Client.ts">deleteTool</a>(toolId) -> Sonyk.SuccessResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Delete a tool

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.tools.deleteTool("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**toolId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Tools.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

## Assets

<details><summary><code>client.assets.<a href="/src/api/resources/assets/client/Client.ts">listAgentAssets</a>(agentId, { ...params }) -> Sonyk.AssetListResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve all knowledge base assets for a specific agent with pagination and filtering.

Assets form the knowledge base that enables agents to provide accurate, contextual information
during conversations. The system supports multiple asset types and intelligent processing:

## Supported Asset Types

- **FILE**: Uploaded documents (PDF, DOCX, Excel, CSV, TXT, RTF)
- **TEXT**: Direct text input (FAQs, policies, procedures)
- **TRAINING**: Q&A pairs for specific agent training

## Processing Pipeline

1. **Secure Upload**: Files validated and stored safely
2. **Text Extraction**: Advanced parsers extract clean text from files
3. **AI Enhancement**: OCR errors corrected, formatting cleaned
4. **Smart Chunking**: Content divided into optimal retrieval segments
5. **Vector Embeddings**: Semantic search capabilities enabled
6. **Cloud Storage**: Secure storage with version control

## Use Cases

- Product documentation and manuals
- Company policies and procedures
- FAQ and help content
- Training materials and scripts
- Customer service knowledge base
  </dd>
  </dl>
  </dd>
  </dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.assets.listAgentAssets("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", {
    search: "product documentation",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string` — Agent ID to retrieve assets for

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.ListAgentAssetsRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Assets.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="/src/api/resources/assets/client/Client.ts">getAgentAssetDetails</a>(agentId, assetId) -> Sonyk.AssetDetailedResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve comprehensive information about a specific asset including processing details and content chunks.

## Response Details

- Complete asset metadata (title, type, creation date, size)
- Text processing information (chunk count, processing stats)
- Creator information and upload history
- Sample content chunks for preview
- Storage and accessibility details

## Processing Information

The response includes details about how the asset was processed:

- Original text length vs. processed length
- Number of chunks created for search
- Embedding model used for semantic search
- Text sanitization and enhancement applied
  </dd>
  </dl>
  </dd>
  </dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.assets.getAgentAssetDetails("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**assetId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Assets.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="/src/api/resources/assets/client/Client.ts">updateAgentAsset</a>(agentId, assetId, { ...params }) -> Sonyk.UpdateAgentAssetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Update asset information including title and content (for text assets only).

## Update Capabilities

- **Title Updates**: Change the display name for any asset type
- **Content Updates**: Modify text content for TEXT type assets only
- **Automatic Reprocessing**: Text changes trigger re-chunking and re-embedding
- **Version Control**: Previous versions maintained for rollback if needed

## File Assets

File assets (PDF, DOCX, etc.) cannot have their content updated through this endpoint.
To update file content, delete the existing asset and upload a new file.

## Processing Impact

When text content is updated:

- Existing chunks are replaced with new ones
- Vector embeddings are regenerated
- Search index is updated immediately
- Agent has access to updated information within seconds
  </dd>
  </dl>
  </dd>
  </dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.assets.updateAgentAsset("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**assetId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.UpdateAgentAssetRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Assets.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="/src/api/resources/assets/client/Client.ts">deleteAgentAsset</a>(agentId, assetId) -> Sonyk.DeleteAgentAssetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Permanently delete an asset from the agent's knowledge base.

## Deletion Process

1. **Immediate Removal**: Asset becomes unavailable to the agent instantly
2. **Chunk Cleanup**: All text chunks removed from search database
3. **Storage Cleanup**: Files deleted from cloud storage
4. **Permanent Action**: Deletion cannot be undone

## Impact on Agent Performance

- Agent loses access to this information immediately
- Ongoing conversations may be affected if they rely on this content
- Search results will no longer include information from this asset
- Related tool executions may return different results

## Best Practices

- Ensure the asset is no longer needed before deletion
- Consider updating content instead of deleting when possible
- Test agent performance after removing significant knowledge sources
- Maintain backups of important content outside the system
  </dd>
  </dl>
  </dd>
  </dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.assets.deleteAgentAsset("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**assetId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Assets.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="/src/api/resources/assets/client/Client.ts">uploadAgentAsset</a>(agentId, { ...params }) -> Sonyk.UploadAgentAssetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Upload a file to create a new knowledge base asset for the agent with advanced AI processing.

## Supported File Types & Processing

### Documents

- **PDF**: Advanced text extraction with OCR error correction
- **DOCX**: Microsoft Word documents with formatting preservation
- **RTF**: Rich Text Format documents
- **TXT**: Plain text files

### Spreadsheets

- **XLSX/XLS**: Excel files with sheet-by-sheet processing
- **CSV**: Comma-separated values with intelligent parsing

## AI-Enhanced Processing Pipeline

### 1. Secure Upload & Validation

- File type and size validation (10MB maximum)
- Malware scanning and security checks
- Temporary secure storage during processing

### 2. Intelligent Text Extraction

- **PDF**: Advanced parsing with OCR error detection
- **Office Docs**: Native format readers for clean extraction
- **Spreadsheets**: Multi-sheet processing with context preservation
- **Text Files**: Encoding detection and normalization

### 3. AI-Powered Content Enhancement

- **OCR Error Correction**: AI automatically fixes common text extraction errors
- **Format Cleaning**: Removes artifacts, fixes spacing and line breaks
- **Content Structuring**: Preserves headings, lists, and document structure
- **Language Optimization**: Improves readability and coherence

### 4. Smart Chunking Strategy

- **Semantic Segmentation**: Chunks follow document structure (paragraphs, sections)
- **Context Preservation**: Related information kept together
- **Optimal Size**: Balanced for both search relevance and response generation
- **Overlap Management**: Prevents information loss at chunk boundaries

### 5. Vector Embedding Generation

- **Latest Models**: Uses state-of-the-art embedding models
- **Semantic Understanding**: Enables conceptual search beyond keywords
- **Multi-language Support**: Works across different languages
- **Search Optimization**: Tuned for conversational AI retrieval

### 6. Secure Cloud Storage

- **Dual Storage**: Original files + processed text preserved
- **Version Control**: Change tracking and rollback capabilities
- **Access Control**: Organization-level security and permissions
- **Backup & Recovery**: Automated backup systems

## Quality Assurance

- **Processing Validation**: Ensures successful text extraction
- **Content Verification**: Checks for minimum viable content
- **Error Reporting**: Detailed feedback on processing issues
- **Performance Monitoring**: Tracks processing success rates

## Use Cases

- **Product Manuals**: Technical documentation and user guides
- **Policy Documents**: Company policies and procedures
- **Training Materials**: Educational content and SOPs
- **FAQ Collections**: Customer service knowledge bases
- **Research Papers**: Academic and technical documents
- **Spreadsheet Data**: Product catalogs, pricing, specifications
  </dd>
  </dl>
  </dd>
  </dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.assets.uploadAgentAsset("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", {
    file: fs.createReadStream("/path/to/your/file"),
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.UploadAgentAssetRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Assets.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="/src/api/resources/assets/client/Client.ts">createAgentTextAsset</a>(agentId, { ...params }) -> Sonyk.CreateAgentTextAssetResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Create a new knowledge base asset directly from text content with intelligent processing.

## Ideal Use Cases

### Frequently Asked Questions (FAQs)

Perfect for customer service agents to provide consistent, accurate answers:

```
# Customer Service FAQ

## Q: What are your business hours?
A: We are open Monday to Friday, 9 AM to 6 PM EST.

## Q: How can I return a product?
A: Visit our returns page or call customer service within 30 days.
```

### Company Policies & Procedures

Ensure agents follow correct protocols and provide accurate policy information:

```
# Refund Policy

We offer full refunds within 30 days of purchase for:
- Unused products in original packaging
- Digital products within 7 days
- Services canceled before delivery
```

### Product Information & Specifications

Enable agents to answer detailed product questions:

```
# Product Specifications - Model XYZ

## Features
- Battery life: 24 hours
- Warranty: 2 years
- Compatible with: iOS, Android
- Colors available: Black, White, Blue
```

### Training Scripts & Guidelines

Provide agents with conversation templates and best practices:

```
# Call Opening Scripts

## For New Customers
"Thank you for calling [Company]. I'm [Name], and I'm here to help you today."

## For Returning Customers
"Welcome back to [Company]! How can I assist you today?"
```

## Processing Features

### Intelligent Text Structuring

- **Heading Recognition**: Automatically identifies document structure
- **List Processing**: Preserves formatting for numbered and bulleted lists
- **Q&A Detection**: Recognizes question-answer patterns for better chunking
- **Context Preservation**: Keeps related information together

### Smart Chunking Algorithm

- **Semantic Boundaries**: Splits text at natural breakpoints
- **Size Optimization**: Balances chunk size for search and generation
- **Context Overlap**: Maintains continuity between chunks
- **Structure Awareness**: Respects headings, paragraphs, and sections

### Search Optimization

- **Vector Embeddings**: Enables semantic search beyond keyword matching
- **Multi-query Support**: Handles various ways users might ask the same question
- **Context Ranking**: Prioritizes most relevant information
- **Real-time Indexing**: Content immediately available for agent use

## Content Guidelines

### Structure Your Content

- Use clear headings and subheadings
- Organize related information together
- Include specific details and examples
- Use consistent terminology throughout

### Optimize for Search

- Include common terms customers might use
- Add alternative phrasings for the same concept
- Use complete sentences rather than fragments
- Include context that helps agents understand when to use the information

### Keep It Current

- Regular updates ensure accuracy
- Version control helps track changes
- Remove outdated information promptly
- Test agent responses after updates
  </dd>
  </dl>
  </dd>
  </dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.assets.createAgentTextAsset("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", {
    text: "# Customer Service FAQ - Updated January 2025\n\n## Business Information\n\n### Q: What are your business hours?\nA: We are open Monday to Friday from 9 AM to 6 PM EST. Weekend support is available via email only.\n\n### Q: Where are you located?\nA: Our headquarters is at 123 Business St, City, State 12345. We also have locations in Chicago and Miami.\n\n## Product Support\n\n### Q: How do I return a product?\nA: Returns are easy! Visit our website's return portal, print a shipping label, and send the item back within 30 days. Refunds are processed within 5-7 business days.\n\n### Q: What's your warranty policy?\nA: All products come with a standard 1-year warranty. Extended warranties up to 3 years are available for purchase.\n\n## Account Management\n\n### Q: How do I reset my password?\nA: Click 'Forgot Password' on the login page, enter your email, and follow the instructions sent to your inbox. The reset link expires in 24 hours.\n\n### Q: Can I change my subscription plan?\nA: Yes! Log into your account, go to Settings > Subscription, and select your new plan. Changes take effect immediately.\n",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.CreateAgentTextAssetRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Assets.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="/src/api/resources/assets/client/Client.ts">getAgentAssetContent</a>(agentId, assetId) -> Sonyk.GetAgentAssetContentResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Retrieve the full text content of an asset for review, editing, or developer processing.

## Content Details

Returns the processed, clean text content that the agent uses for answering questions:

### For File Assets (PDF, DOCX, etc.)

- **Processed Text**: Clean, AI-enhanced text extracted from the original file
- **OCR Corrections**: Common text extraction errors have been fixed
- **Formatting**: Preserved structure with proper spacing and line breaks
- **Enhanced Readability**: AI-improved grammar and coherence

### For Text Assets

- **Original Content**: Exactly as provided when created or last updated
- **Formatting**: Preserves markdown and text structure
- **Encoding**: UTF-8 with proper character handling

## Use Cases

### Content Review & Quality Assurance

- Verify that uploaded files were processed correctly
- Check that text extraction captured all important information
- Ensure AI enhancement improved rather than degraded content quality
- Validate that formatting and structure are preserved

### Content Editing & Updates

- Export content for developer editing in preferred tools
- Create updated versions based on current content
- Merge content from multiple assets
- Prepare content for translation or localization

### Integration & Automation

- Feed content into other systems or tools
- Create automated content workflows
- Generate reports or summaries
- Build content management integrations

### Backup & Archival

- Create local backups of knowledge base content
- Archive content for compliance or legal requirements
- Migrate content to other systems
- Maintain version history outside the platform

## Response Information

The response includes both the content and useful metadata:

- **Content Length**: Character count for processing planning
- **Creation Date**: When the asset was originally created
- **Asset Type**: Whether it's a file upload or direct text input
- **Processing Status**: Information about how the content was processed
  </dd>
  </dl>
  </dd>
  </dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.assets.getAgentAssetContent("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx");
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**assetId:** `string`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Assets.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

<details><summary><code>client.assets.<a href="/src/api/resources/assets/client/Client.ts">searchAgentAssets</a>(agentId, { ...params }) -> Sonyk.SearchAgentAssetsResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Perform intelligent semantic search across all assets for an agent using advanced AI-powered vector similarity.

## How Semantic Search Works

Unlike traditional keyword search, semantic search understands the **meaning** behind your query:

### Traditional Keyword Search

- Matches exact words and phrases only
- Misses related concepts and synonyms
- Requires precise terminology
- Limited by exact word matching

### AI-Powered Semantic Search

- **Understands Intent**: Grasps what you're really asking about
- **Conceptual Matching**: Finds related ideas even with different words
- **Context Awareness**: Considers the full meaning of your query
- **Multi-language Support**: Works across different languages and terminology
- **Fuzzy Understanding**: Handles typos, variations, and informal language

## Search Examples

### Query: "How do I reset my password?"

**Finds content like:**

- "Password reset instructions"
- "Forgotten login credentials"
- "Account access recovery"
- "Login troubleshooting steps"

### Query: "Product warranty information"

**Finds content like:**

- "Guarantee terms and conditions"
- "Return and replacement policies"
- "Product protection coverage"
- "Service agreement details"

### Query: "Business hours"

**Finds content like:**

- "Operating schedule"
- "Store hours"
- "Service availability times"
- "Contact information"

## Retrieval-Augmented Generation (RAG)

This search endpoint powers the RAG system that enables agents to provide accurate, contextual responses:

### 1. Query Understanding

- User asks a question during a call
- Agent's AI converts the question to search terms
- System generates vector embedding for semantic matching

### 2. Knowledge Retrieval

- Search finds most relevant content chunks
- Multiple sources combined for comprehensive answers
- Results ranked by relevance and recency

### 3. Response Generation

- Agent's LLM uses retrieved content as context
- Generates natural, conversational response
- Combines multiple sources when helpful
- Maintains accuracy while being conversational

## Search Parameters & Tuning

### Similarity Threshold (0.0 - 1.0)

Controls how closely results must match your query:

- **0.5-0.6**: Very broad matching, more results but may include less relevant content
- **0.7-0.8**: Balanced matching, good mix of relevance and recall **(recommended)**
- **0.9-1.0**: Strict matching, only very closely related content returned
  </dd>
  </dl>
  </dd>
  </dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.assets.searchAgentAssets("xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx", {
    query: "How do I reset my password?",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**agentId:** `string`

</dd>
</dl>

<dl>
<dd>

**request:** `Sonyk.SearchAgentAssetsRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Assets.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>

## Calls

<details><summary><code>client.calls.<a href="/src/api/resources/calls/client/Client.ts">initiateCall</a>({ ...params }) -> Sonyk.CoreCallResponse</code></summary>
<dl>
<dd>

#### 📝 Description

<dl>
<dd>

<dl>
<dd>

Proxy endpoint to initiate calls through the Sonyk Core API system.
Validates permissions and credits, then forwards request to core.sonyk.io.

</dd>
</dl>
</dd>
</dl>

#### 🔌 Usage

<dl>
<dd>

<dl>
<dd>

```typescript
await client.calls.initiateCall({
    agentId: "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxx",
    toNumber: "+xxxxxxxxxx",
});
```

</dd>
</dl>
</dd>
</dl>

#### ⚙️ Parameters

<dl>
<dd>

<dl>
<dd>

**request:** `Sonyk.InitiateCallRequest`

</dd>
</dl>

<dl>
<dd>

**requestOptions:** `Calls.RequestOptions`

</dd>
</dl>
</dd>
</dl>

</dd>
</dl>
</details>
