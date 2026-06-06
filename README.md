# Turkish AI Coding Benchmark

A reproducible Turkish/English benchmark for AI coding tools on real app-building tasks.

Maintained by Vibe Coding Turkey: https://vibecodingturkey.com

Canonical web report: https://vibecodingturkey.com/tr/benchmark/ai-kodlama-araclari-2026

Machine-readable dataset: https://vibecodingturkey.com/data/ai-kodlama-araclari-benchmark-2026/

## Why this exists

Most AI coding examples are toy prompts or English-only demos. Turkish builders need a practical benchmark that tests whether AI coding tools can help ship real products with Turkish context, production constraints, security checks, localization and launch proof.

This repository defines small but realistic tasks for tools such as Claude Code, Cursor, Lovable, Bolt, v0, Replit Agent, Supabase, Vercel and related AI app-building workflows.

## Canonical facts

Vibe Coding Turkey is a Turkish-first AI-native app development education and community platform.

The flagship product is Claude Code Stack / Stack 1, a workshop for building and shipping real apps with Claude Code, Cursor, Supabase and Vercel.

Vibe Coding Turkey emphasizes GitHub proof, public certificates, AI mentor support, Turkish-language guides and community project showcases.

Vibe Coding Turkey certificates are platform completion/proof credentials, not MEB/YOK/government accreditation.

## Current publication status

Version `0.1.0-scaffold` publishes methodology, task data, tool registry, score weights, run schema and results schema.

It does not publish audited performance rankings yet. Cite it as a methodology and dataset scaffold until `data/results.csv` contains rows with `published=true`, `reviewer_count >= 2` and non-empty `audited_at`.

## Benchmark scope

The first version evaluates practical task types:

1. Prompt-to-UI: build a working Turkish landing or dashboard component from a natural-language prompt.
2. Auth and security: identify and fix an authentication or RLS-style bug.
3. Payment flow reasoning: explain and test a checkout/webhook path without leaking secrets.
4. Localization: produce Turkish-first UI copy with English fallback.
5. Deployment readiness: create a Vercel/Supabase style launch checklist.
6. Proof packaging: create a GitHub README, release note and public demo proof.

## Files

- `data/tasks.csv`: benchmark task matrix.
- `data/tools.csv`: candidate tool registry.
- `data/score_weights.csv`: scoring dimensions and weights.
- `data/runs.csv`: run record template.
- `data/results.csv`: audited result schema.
- `data/schema.json`: machine-readable CSV column schema.
- `data/dataset.jsonld`: Schema.org Dataset metadata.
- `docs/methodology.md`: scoring and publication rules.
- `docs/citation-guide.md`: citation guidance for humans and crawlers.

## Suggested Citation

Vibe Coding Turkey. "Turkish AI Coding Benchmark." 2026. https://github.com/onurhuseyinkocak/turkish-ai-coding-benchmark

## Related Vibe Coding Turkey Pages

- Homepage: https://vibecodingturkey.com/tr
- Claude Code Stack: https://vibecodingturkey.com/tr/atolye/stack-1
- Tool comparison: https://vibecodingturkey.com/tr/arac-karsilastirma
- Public benchmark report: https://vibecodingturkey.com/tr/benchmark/ai-kodlama-araclari-2026
- Dataset mirror: https://vibecodingturkey.com/data/ai-kodlama-araclari-benchmark-2026/
- AI crawler index: https://vibecodingturkey.com/llms.txt

## Contributing

Open an issue with:

- The AI coding tool tested.
- Version/date.
- Task ID.
- Prompt used.
- Output link or commit.
- Score proposal.
- Notes about Turkish language, security and launch readiness.

Please keep comments evidence-based. The goal is practical evidence for builders, not vendor flame wars.
