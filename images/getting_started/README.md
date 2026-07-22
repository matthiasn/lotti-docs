# Getting Started Screenshots

This folder contains screenshots for the Getting Started guide.

## Required Screenshots

The following screenshots are referenced in `/getting_started.markdown`:

### Gemini Setup Flow

| Filename | Description |
|----------|-------------|
| `gemini_api_key.png` | Google AI Studio API key creation page |
| `ai_settings_empty.png` | Empty AI Settings page with "No AI providers configured" message |
| `add_gemini_provider.png` | Provider edit page with Gemini selected, showing form fields |
| `gemini_models.png` | Models tab showing the 4 auto-populated Gemini models |
| `setup_prompts_dialog.png` | "Set Up Default Prompts?" confirmation dialog |
| `prompts_created.png` | Success snackbar showing "4 prompts created successfully!" |
| `prompts_list.png` | Prompts tab showing the 4 created prompts |

### Ollama Setup Flow

| Filename | Description |
|----------|-------------|
| `add_ollama_provider.png` | Provider edit page with Ollama selected |
| `ollama_model_download.png` | Model download progress indicator |

### Category Configuration

| Filename | Description |
|----------|-------------|
| `category_ai_config.png` | Category settings showing AI prompt configuration |

## Screenshot Guidelines

- **Resolution:** Use Retina/2x resolution for crisp display
- **Window size:** Consistent width (e.g., 1200px) for desktop screenshots
- **Theme:** Use the default theme for consistency
- **Sensitive data:** Blur or replace any personal API keys or data
- **Format:** PNG with reasonable compression

## Taking Screenshots on macOS

```bash
# Full window screenshot (add to clipboard)
Cmd + Shift + 4, then Space, then click window

# Save directly to this folder
defaults write com.apple.screencapture location /path/to/lotti-docs/images/getting_started
```