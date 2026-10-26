# AI-Verse maintained routing patch

AI-Verse owns this maintained dependency revision. Upstream acceptance is not
required for AI-Verse use. The original MIT license and copyright remain in LICENSE.

Base: 5483a0e1eef15b467c167e95796791112cedbb7c (previous Dashboard audited pin).
Delta: preserve explicit local, Ollama, LM Studio and LiteLLM provider prefixes
until provider selection. Only the local HTTP request builder removes the prefix;
local/aiverse reaches the configured Gateway with model aiverse.

The focused synthetic regression covers local/namespaced/case variants, existing
OpenAI/Anthropic aliases and no fallback after local authentication failure.
Validate with `corepack pnpm exec vitest run src/lib/__tests__/task-dispatch-local-routing.test.ts`.
Dashboard owns the composed HTTP test and separate owner acceptance record.
