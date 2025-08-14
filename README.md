# Sonyk TypeScript Library

[![fern shield](https://img.shields.io/badge/%F0%9F%8C%BF-Built%20with%20Fern-brightgreen)](https://buildwithfern.com?utm_source=github&utm_medium=github&utm_campaign=readme&utm_source=https%3A%2F%2Fgithub.com%2Fws-github-admin%2Fsonyk-ts-sdk)
[![npm shield](https://img.shields.io/npm/v/sonyk-sdk)](https://www.npmjs.com/package/sonyk-sdk)

The Sonyk TypeScript library provides convenient access to the Sonyk API from TypeScript.

## Installation

```sh
npm i -s sonyk-sdk
```

## Reference

A full reference for this library is available [here](https://github.com/ws-github-admin/sonyk-ts-sdk/blob/HEAD/./reference.md).

## Usage

Instantiate and use the client with the following:

```typescript
import { SonykClient } from "sonyk-sdk";

const client = new SonykClient({ apiKey: "YOUR_API_KEY" });
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

## Request And Response Types

The SDK exports all request and response types as TypeScript interfaces. Simply import them with the
following namespace:

```typescript
import { Sonyk } from "sonyk-sdk";

const request: Sonyk.ListAgentsRequest = {
    ...
};
```

## Exception Handling

When the API returns a non-success status code (4xx or 5xx response), a subclass of the following error
will be thrown.

```typescript
import { SonykError } from "sonyk-sdk";

try {
    await client.agents.createAgent(...);
} catch (err) {
    if (err instanceof SonykError) {
        console.log(err.statusCode);
        console.log(err.message);
        console.log(err.body);
        console.log(err.rawResponse);
    }
}
```

## Advanced

### Additional Headers

If you would like to send additional headers as part of the request, use the `headers` request option.

```typescript
const response = await client.agents.createAgent(..., {
    headers: {
        'X-Custom-Header': 'custom value'
    }
});
```

### Additional Query String Parameters

If you would like to send additional query string parameters as part of the request, use the `queryParams` request option.

```typescript
const response = await client.agents.createAgent(..., {
    queryParams: {
        'customQueryParamKey': 'custom query param value'
    }
});
```

### Retries

The SDK is instrumented with automatic retries with exponential backoff. A request will be retried as long
as the request is deemed retryable and the number of retry attempts has not grown larger than the configured
retry limit (default: 2).

A request is deemed retryable when any of the following HTTP status codes is returned:

- [408](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/408) (Timeout)
- [429](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/429) (Too Many Requests)
- [5XX](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/500) (Internal Server Errors)

Use the `maxRetries` request option to configure this behavior.

```typescript
const response = await client.agents.createAgent(..., {
    maxRetries: 0 // override maxRetries at the request level
});
```

### Timeouts

The SDK defaults to a 60 second timeout. Use the `timeoutInSeconds` option to configure this behavior.

```typescript
const response = await client.agents.createAgent(..., {
    timeoutInSeconds: 30 // override timeout to 30s
});
```

### Aborting Requests

The SDK allows users to abort requests at any point by passing in an abort signal.

```typescript
const controller = new AbortController();
const response = await client.agents.createAgent(..., {
    abortSignal: controller.signal
});
controller.abort(); // aborts the request
```

### Access Raw Response Data

The SDK provides access to raw response data, including headers, through the `.withRawResponse()` method.
The `.withRawResponse()` method returns a promise that results to an object with a `data` and a `rawResponse` property.

```typescript
const { data, rawResponse } = await client.agents.createAgent(...).withRawResponse();

console.log(data);
console.log(rawResponse.headers['X-My-Header']);
```

### Runtime Compatibility

The SDK works in the following runtimes:

- Node.js 18+
- Vercel
- Cloudflare Workers
- Deno v1.25+
- Bun 1.0+
- React Native

### Customizing Fetch Client

The SDK provides a way for you to customize the underlying HTTP client / Fetch function. If you're running in an
unsupported environment, this provides a way for you to break glass and ensure the SDK works.

```typescript
import { SonykClient } from "sonyk-sdk";

const client = new SonykClient({
    ...
    fetcher: // provide your implementation here
});
```

## Contributing

While we value open-source contributions to this SDK, this library is generated programmatically.
Additions made directly to this library would have to be moved over to our generation code,
otherwise they would be overwritten upon the next generated release. Feel free to open a PR as
a proof of concept, but know that we will not be able to merge it as-is. We suggest opening
an issue first to discuss with us!

On the other hand, contributions to the README are always very welcome!
