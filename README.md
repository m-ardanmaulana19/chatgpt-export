# Export OpenAI ChatGPT Conversations (chatgpt-export) [TEMPORARY CHAT specifically]

[![GitHub license](https://img.shields.io/github/license/ryanschiang/chatgpt-export)](
    ./LICENSE
)
[![Github Stars](https://img.shields.io/github/stars/ryanschiang/chatgpt-export?style=social)](
    https://github.com/ryanschiang/chatgpt-export/stargazers
)

![Working as of March 20, 2024](https://img.shields.io/badge/working%20as%20of-%20march%2020,%202024-blue)

This browser script formats and downloads ChatGPT conversations to markdown, JSON, and PNG for sharing and exporting chat logs.

You can export the active ChatGPT chat log directly from the browser console, entirely locally. No data is sent to any server.

**Supports the latest ChatGPT web UI as of March 20, 2024.**

## Usage

 1. Navigate to [https://chatgpt.com/?model=gpt-4o&temporary-chat=true](https://chatgpt.com/?model=gpt-4o&temporary-chat=true).
 2. Open the chat thread you'd like to export.
 3. Open the browser console (how to open console: [Chrome](https://developer.chrome.com/docs/devtools/open), [Firefox](https://firefox-source-docs.mozilla.org/devtools-user/), [Safari](https://developer.apple.com/library/archive/documentation/NetworkingInternetWeb/Conceptual/Web_Inspector_Tutorial/EnableWebInspector/EnableWebInspector.html))
 4. Follow the below steps depending on which output type you'd like.

 > [!IMPORTANT]  
> Always be careful when pasting code into the console. Only paste code from trusted sources, as it can be used to execute malicious code.
> You can explore this repository and verify the code before pasting it into the console, or clone and build the code yourself.

### JSON

1. Copy contents of [`/dist/json.min.js`](./dist/json.min.js)
2. Paste into browser console

#### Example output (JSON export)

```json
{
    "meta": {
        "title": "Fetch API: Modern HTTP Requests",
        "exportedAt": "2024-03-20 09:01:10"
    },
    "chats": [
        {
            "index": 0,
            "type": "prompt",
            "message": [
                {
                    "type": "p",
                    "data": "How do I send a request with Javascript?"
                }
            ]
        },
        {
            "index": 1,
            "type": "response",
            "message": [
                {
                    "type": "p",
                    "data": "To send a request in JavaScript, you typically use either the XMLHttpRequest object or the more modern Fetch API. Given your expertise and the trend towards modern, more efficient, and promise-based solutions, I recommend using the Fetch API for most use cases. It's more powerful and flexible, aligning with contemporary JavaScript practices."
                },
                {
                    "type": "p",
                    "data": "Using Fetch API"
                },
            ]
        }
    ]
}
```



## Limitations

This is a trivial implementation as ChatGPT currently does not support sharing or exporting conversations. It may break with future changes.

It currently supports:
- Paragraphs / Text
- Lists
- Code blocks
- Tables
- Headings


## Acknowledgements

- [html2canvas](https://github.com/niklasvh/html2canvas) - Used to take a screenshot of the chat log and export as a PNG.

## You May Also Like

[`claude-export`](https://github.com/ryanschiang/claude-export) - Export Anthropic Claude conversations to markdown, JSON, and PNG for sharing and exporting chat logs.

## Future Development

- [ ] Nested code blocks (within lists)
- [ ] Nested lists
- [x] Trim whitespace on exported images
