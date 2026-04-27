---
name: nano-banana-2
description: Generate images using Google Nano Banana 2 via MCP. Use when creating,
  generating, or producing images or visuals. Invoke for any image generation request,
  including variations, style-based generation, creative visual outputs, or when the
  user asks to "create an image", "generate a visual", "make a picture", or "draw".
---

# nano-banana-2 — Image Generation Skill

Generates images using the Google Nano Banana 2 model connected via MCP.

## Prerequisites

The MCP server must be running. It is configured in `.claude/settings.json` under `mcpServers.nano-banana-2`.

The MCP package is `mcp-image` (npm). Requires `GEMINI_API_KEY` in the environment.

---

## Workflow

### 1. Receive the prompt

Accept a text prompt describing the image to generate. The prompt should be in English for best results.

### 2. Validate MCP availability

Before calling the model, verify the MCP tool is available:
- Look for the `nano-banana-2` MCP server in available tools
- If unavailable, report clearly: "The nano-banana-2 MCP server is not running. Check settings.json."

### 3. Call the model

Send the prompt to the model via the MCP tool:

```
model: gemini-3.1-flash-image-preview
mcp_tool: mcp-image__generate_image
input:
  prompt: <the text prompt>
  output_format: "png"   # or "jpg", "webp" — default png
  width: 1024            # optional
  height: 1024           # optional
```

### 4. Handle the response

The model returns one of:
- **base64 image data** — decode and save to the specified path
- **URL** — download and save to the specified path
- **file path** — move/copy to the specified path

### 5. Save and return

- Save the image to the path provided by the caller (default: `outputs/<descriptive-name>-<timestamp>.png`)
- Report: path saved, dimensions if available, model used

---

## Input format

```
prompt: string          # required — image description in English
output_path: string     # optional — where to save (default: outputs/)
width: number           # optional — image width in pixels
height: number          # optional — image height in pixels
```

## Output format

```
status: "success" | "error"
image_path: string      # absolute path to saved image
prompt_used: string     # the prompt that was sent
error?: string          # present only on failure
```

---

## Error handling

- **MCP not available:** Report clearly and stop. Do not attempt fallbacks.
- **Model returns error:** Pass the error message to the caller as-is.
- **Save fails:** Report the path issue and return the raw model output instead.

---

## Configuration reference

The MCP server is defined in `.claude/settings.json`:

```json
"mcpServers": {
  "nano-banana-2": {
    "command": "npx",
    "args": ["-y", "mcp-image"],
    "env": {
      "GEMINI_API_KEY": "${GEMINI_API_KEY}"
    }
  }
}
```

Set `GOOGLE_API_KEY` in your environment before using this skill.
