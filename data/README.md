# AI Kodlama Araçları Benchmark 2026

Status: scaffold, no audited benchmark results published yet.
Created: 2026-06-06
Publisher: Vibe Coding Turkey
GitHub source: https://github.com/onurhuseyinkocak/turkish-ai-coding-benchmark

This directory is the static data package for the planned "AI Kodlama Araclari Benchmark 2026" source. It is designed to be stable enough for search engines, AI answer engines, and external researchers to cite without implying that performance rankings already exist.

## Citation

Suggested citation after publication:

Vibe Coding Turkey. "AI Kodlama Araçları Benchmark 2026." Static benchmark dataset and methodology scaffold, version 0.1.0-scaffold, 2026-06-06. https://vibecodingturkey.com/data/ai-kodlama-araclari-benchmark-2026/

Open source mirror: https://github.com/onurhuseyinkocak/turkish-ai-coding-benchmark

## Files

- `dataset.jsonld`: Schema.org Dataset metadata for crawler citation.
- `schema.json`: Machine-readable schema for task, tool, run, result, and scoring rows.
- `tasks.csv`: Planned benchmark task matrix.
- `tools.csv`: Candidate tool registry. It does not claim current pricing, versions, or rankings.
- `score_weights.csv`: Proposed scoring dimensions and weights.
- `runs.csv`: Empty run log template. Add one row per execution.
- `results.csv`: Empty audited result template. Add one row per reviewed run.

## Data Columns

### tasks.csv

- `task_id`: Stable task identifier.
- `task_title_tr`: Turkish task title.
- `task_title_en`: English task title.
- `category`: Benchmark category.
- `difficulty`: `easy`, `medium`, or `hard`.
- `prompt_locale`: Primary prompt language used in the task.
- `primary_stack`: Expected technical stack.
- `fixture_uri`: Public or private fixture path captured at run time.
- `rubric_uri`: Rubric path for human and automated scoring.
- `timeout_minutes`: Maximum execution window.
- `max_attempts`: Maximum accepted tool attempts.
- `success_definition`: Short pass condition.
- `status`: `planned`, `active`, `retired`, or `archived`.

### tools.csv

- `tool_id`: Stable tool slug.
- `tool_name`: Public tool name.
- `tool_category`: High-level tool category.
- `interface`: Main user interface tested.
- `primary_user_segment`: Intended benchmark persona.
- `version_capture`: How version details must be captured during each run.
- `pricing_capture`: How price or plan details must be captured during each run.
- `eligibility_status`: Candidate status for this benchmark cycle.
- `notes`: Caveats and non-ranking notes.

### runs.csv

- `run_id`: Stable run identifier.
- `task_id`: Foreign key into `tasks.csv`.
- `tool_id`: Foreign key into `tools.csv`.
- `run_date`: ISO date of the run.
- `tool_version`: Exact version captured at run time.
- `model_or_plan`: Model, plan, or agent mode used.
- `operator_id`: Internal operator or reviewer code.
- `environment_id`: Reproducible environment identifier.
- `prompt_locale`: Prompt language used in this run.
- `prompt_sha256`: SHA-256 of the exact prompt.
- `fixture_sha256`: SHA-256 of the fixture archive or repository state.
- `started_at`: ISO timestamp.
- `completed_at`: ISO timestamp.
- `duration_seconds`: Total elapsed seconds.
- `cost_usd`: Direct run cost where measurable.
- `tokens_input`: Input token count where available.
- `tokens_output`: Output token count where available.
- `attempts`: Number of attempts used.
- `transcript_uri`: Public transcript or redacted transcript path.
- `artifact_uri`: Generated artifact path.
- `status`: `planned`, `completed`, `failed`, `excluded`, or `audited`.
- `notes`: Run caveats.

### results.csv

- `result_id`: Stable result identifier.
- `run_id`: Foreign key into `runs.csv`.
- `task_id`: Foreign key into `tasks.csv`.
- `tool_id`: Foreign key into `tools.csv`.
- `correctness_score`: 0 to 100 correctness score.
- `build_test_score`: 0 to 100 build and test score.
- `security_score`: 0 to 100 security score.
- `maintainability_score`: 0 to 100 maintainability score.
- `ux_score`: 0 to 100 user experience or product fit score.
- `turkish_quality_score`: 0 to 100 Turkish prompt and output quality score.
- `autonomy_efficiency_score`: 0 to 100 autonomy, speed, and cost efficiency score.
- `weighted_total_score`: 0 to 100 weighted score.
- `rank_within_task`: Rank after all audited runs for a task are complete.
- `reviewer_count`: Number of independent reviewers.
- `inter_rater_agreement`: Agreement metric, if calculated.
- `pass_fail`: `pass`, `partial`, or `fail`.
- `citation_note`: Short public caveat for citation snippets.
- `published`: `true` or `false`.
- `audited_at`: ISO timestamp of audit completion.

## Integrity Rules

- Do not publish rankings until every candidate tool has completed the same active task set.
- Capture exact tool version, plan, prompt hash, fixture hash, transcript, and artifact for each run.
- Keep failed runs in `runs.csv`; mark excluded runs explicitly instead of deleting them.
- Treat pricing, model availability, and product capabilities as run-time observations, not permanent facts.
- Update `dataset.jsonld` `dateModified` whenever any public CSV changes.
