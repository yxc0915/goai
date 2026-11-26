# GoAI Downstream Fork (`aiword-harness`)

- **Upstream**: https://github.com/zendev-sh/goai (`upstream/main`)
- **Downstream Fork**: https://github.com/yxc0915/goai (`origin/aiword-harness`)
- **License**: MIT License (permissive commercial use, modification, and redistribution; original MIT `LICENSE` preserved)

## Purpose in AI Word

This repository serves as the core multi-provider LLM wire-protocol conversion engine for `f:\project2\wdzs\document-harness` (via Go `replace github.com/zendev-sh/goai => ../vendor-goai`), providing native streaming, tool calling, prompt caching, and reasoning/thought signature replay across:

- OpenAI Responses API (`/v1/responses`)
- OpenAI Chat Completions & Generic OpenAI-Compatible Fallback (`compat`)
- Anthropic Messages API (`/v1/messages`, Extended Thinking + signatures)
- Google Gemini Native API (`streamGenerateContent`, `thoughtSignature`)
- DeepSeek, Azure OpenAI, OpenRouter

All BYOK HTTP requests inject AI Word's post-DNS SSRF-hardened `*http.Client` via each provider's `WithHTTPClient` option.

## Syncing Upstream Updates

From the workspace root `f:\project2\wdzs`:

```powershell
.\scripts\sync-goai-upstream.ps1 -Push
```
