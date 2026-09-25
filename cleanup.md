# Cleanup

Context dump for three recurring request families in the prompt history: simplification and deletion, docs writing and cleanup, de-slop / not-AI-looking. The three labels were picked by the user from the ranked pattern inventory; the deliverable was first tried as a skill and then changed to this single document.

Everything below is a verbatim prompt from the history, a verbatim line from a stored file, or a count from the mining run. No rules or recommendations were added. Quotes keep their typos; em dashes and curly quotes inside quotes are normalized to ASCII per the user's style rule.

## This thread

- The three labels: "Simplification & deletion", "Docs writing & cleanup", "De-slop / not-AI-looking".
- Scope: generic, cross-project patterns only. Excluded as project or domain specific: "Billing/Stripe, enterprise readiness, email/template work, database migrations, audio/video pipelines, specific repo stacks, Linear ticket contents, individual feature requests."
- The instruction that defines this file: "lets not include your opinion or invent things that wasnt requested do not invent things by yourself thats like a dumpground for all the context aroudj that"

## Counts

Base: `~/.claude/history.jsonl`, 6,537 prompts, 751 sessions, 51 project cwds, Aug 1 to Sep 25 2026. Counts are intent-based estimates unless marked regex or transcripts.

| Pattern | Prompts (est) | Projects | Cross-checks |
|---|---|---|---|
| Simplification, deletion, cleanup | ~250 | 20-27 | chunk totals 257; regex 319 at ~75% precision (corrected range 205-270); duplicates 195 prompts / 20 projects |
| Docs writing and cleanup | ~180 | 19-23 | chunk totals 178; docs regex 200 at ~95% precision (range 170-200); duplicates 148 prompts / 19 projects |
| De-slop / not-AI-looking | ~160 | 13+ | chunk total 163; "slop" in 35 prompts / 9 projects; /unslop 36 invocations |
| Correction loop around all three | ~510 | 25+ | 34.9% of sessions contain a correction; 26.4% high-signal; median first correction at prompt 3 |

Per-chunk counts from the 9 full-history readers:

| Report | Simplification, deletion | Docs | De-slop |
|---|---|---|---|
| chunk-01 | ~25 prompts, 9 projects | ~9 prompts, 6 projects | ~8 prompts, 3 projects |
| chunk-02 | ~18 prompts, 6 projects | ~21 prompts, 5 projects | ~30 prompts, 7 projects |
| chunk-03 | ~40 prompts, 4 projects | ~16 prompts, 4 projects | ~10 prompts, 3 projects |
| chunk-04 | ~50 prompts, 7 projects | ~28 prompts, 5 projects | ~20 prompts, 4 projects |
| chunk-05 | ~30 prompts, 6 projects | ~19 prompts, 6 projects | ~15 prompts, 5 projects |
| chunk-06 | ~30 prompts, 5 projects | ~40 prompts, 5 projects | ~16 prompts, 5 projects |
| chunk-07 | ~30 prompts, 4 projects | ~30 prompts, 3 projects | ~30 prompts, 4 projects |
| chunk-08 | ~25 prompts, 6 projects | ~9 prompts, 2 projects | ~22 prompts, 4 projects |
| chunk-09 | ~9 prompts, 6 projects | ~6 prompts, 4 projects | not reported |
| Total | 257 | 178 | 151+ |

Weekly share of prompts, from the trends run (7 full weeks, overlap allowed):

| Pattern | Overall | First 3 weeks | Last 3 weeks | Class |
|---|---|---|---|---|
| simplify_delete | 4.9% | 5.2% | 4.7% | steady |
| docs | 3.2% | 2.8% | 3.1% | steady |
| deslop | 1.9% | 0.4% | 3.5% | rising (peak week 4.9%) |

Projects reached: simplification 52.9% of active projects in a week on average; docs 47.1%; deslop 29.4%.

## Simplification and deletion

### Prompt quotes

chunk-01 (Aug 1-11, ~25 prompts, 9 projects)

- "Also, we don't need any other skill. So I think we can simplify our code a lot."
- "DELETE uigraph-ai-artifacts.json"
- "cleanup this repo... we have a big application here.. we don't need any of them.. keep the skeleton remove actual things"
- "remove capText, capPayload They are totally... They are absolutely nonsense. You don't need any kind of capacity limitation."
- "Dont overkill, we only need role level things, not full thing"
- "And do not make it fancy. Keep it as stupid simple as possible. It should be extremely simple minimal design."
- "The UI looks totally garbage every single has input has Extremely garbage information on the bottom of it It's extremely ugly. It's extremely bloated. It's extremely useless"

chunk-02 (Aug 11-13, ~18 prompts, 6 projects)

- "check this folder cleanup EVERYTHING.. everything" (mlflow-explore)
- "Wipe it again, motherfucker. I never say to train anything. I never say to write any readme. Just fucking set up MLflow"
- "WE DO NOT NEED IMAGES FOR buttons at alllll"
- "There are lots of garbage images that I explicitly said to delete."
- "Keep the code stupid simple. The code should be stupid simple and direct. Do not overcomplicate anything."

chunk-03 (Aug 13-18, ~40 prompts, 4 projects: uig, uigraph-ui, mysubs, uigraph-agents; no quotes extracted)

chunk-04 (Aug 19-25, ~50 prompts, 7 projects)

- "you haven;t cleanup the fucing garbage api bullshit you wrote"
- "simplify it... entirely" / "while keeping every details we needed"
- "Can you simplify the code and remove slop?"
- "There are lots of garbage code here. We have to fix all of them. We have to simplify the code. We have to keep the code very simple and flat."
- "I think this is overkill skills/uigraph/references/c4-diagrams.md \n we should keep it simple like: skills/uigraph/references/sequence-diagrams.md"
- Other asks logged: "remove this garbage now", "delete orphan garbages", "Nuke" / "combine migrations", "remove body from log", "reduce the texts", "api not cleaned up"

chunk-05 (Aug 25-Sep 1, ~30 prompts, 6 projects)

- "cleanup graphql layer then as they are unused" (uig)
- "I don't want any garbage freezer. It has to be as stupid fucking simple possible. I repeat again, as stupid fucking simple... There will be no wrapper, there will be no reusable function, there will be nothing like that." (maileditor)
- "src/features/docs/index.ts delete this kinda barrel export garbage" (oiper-web)
- "This entire effect is absolutely unnecessary... its not only useless but also harmful" (uigraph-web)
- "We have two migrations which is not something useful. I think we can merge them into one." (uig)

chunk-06 (Sep 1-6, ~30 prompts, 5 projects)

- "we have to simplify the @maileditor-plugin-next \n we will hvae 3 user, one plugin. ... code will be simple and easy too read"
- "WE DO NOT NEED THE pREVIEW/COPY?DOWNLOAD template remove that pgae"
- "why dowe need src/components/editor-frame.tsx??? \n we have to make it more readbale and flat code"
- "Drop the whisper_backend to transcription_backend rename. ... It adds no behavior. Keeping the old column and writing \"cpu\" for Parakeet removes about ten files from the PR."
- "Can you find similar things where we can make the code simpler?"
- "Just delete the TV; I don't care. Delete the local TV."
- Report's intent line: "remove dead/unneeded pages, files, hooks, vars; flatten code; reduce diff churn; find simplification opportunities."

chunk-07 (~30 prompts, 4 projects: uig, maileditor-frontend, maileditor, dotfiles)

- "keep the code simple man.. lets not overcomplicate that"
- "reduce number of code.. keep it simple man"
- "lets remove those anchors they looks bussy and unnsessary and confusing"
- "avoid using the minimap remomve that"
- "delete espanso + proton vpn entirely from this pc"
- Other asks logged: "remove payrobll", "delete Return an order", "do we need credit_charged?", "remoe this make data form all the nodes"

chunk-08 (Sep 8-16, ~25 prompts, 6 projects)

- "Instead of creating two migrations, let's combine them."
- "I want to avoid touching the database. If something is still, we can keep that, just to reduce the changes."
- "There is a big problem with this. It is very complicated... we have to simplify it a lot."
- "Clean up all the garbage and trash."
- "its not enough.. cleanup more slop"
- "help me to cleanup my docker entirely like all the images, vols, containers etc.. everything"
- "we don't have to show the preview here at all. We can completely remove the preview from here."
- "delete evetying aroud logitech every file etc."

chunk-09 (~9 prompts, 6 projects)

- "delete src/scripts/github-release/main.go and cleanup code"
- "src/demo/index.ts dlee this fila dn aall other barrrel export file delte all of them"
- "lets delete them (the actual things on the uigraph, not local folder)"
- "do we need this?"

duplicates and ngram run

- Theme 4, delete/remove/cleanup plus /unslop: 195 prompts / 20 projects (delete-remove 131 / 17p, cleanup 36 / 12p, unslop 42 / 7p). Examples: "Can you simplify the code and remove slop?", "remove comments", "we have to cleanup this".
- Theme 10, "Simplify / cut scope: too much / keep it simple": 89 prompts / 15 projects. Examples: "still too much", "simplify it... entirely", "thast too much do some basic ones".
- Theme 2, reject generated output: 347 prompts / 21 projects. Examples: "This is extreme level of garbage.", "revert", "[Image #16] make it not slop.. make it professional".
- Theme 8, scope discipline: 96 prompts / 15 projects. Examples: "That's not what I asked for.", "Don't do what I haven't said to do.", "I haven't asked to make a plan... Do not touch the plan in any way."
- Instruction-bearing ngrams: "don't have to" 128, "you don't have" 86, "we don't need" 61, "i don't care" 100, "don't need to" 40, "keep it simple" 23, "i explicitly said" 32, "nothing to do with" 38.

### Stored rules and plans

- `CLAUDE_MD.md:19` "Prioritize simplicity, readability, and directness over reusability or abstraction. Follow YAGNI principles..."
- `CLAUDE_MD.md:19` "Do not introduce variables, functions, helpers, interfaces, types, or other abstractions unless they simplify complex logic or remove substantial repetition."
- `AGENTS_MD.md` "Use the simplest clear, readable, and direct solution that fully satisfies the request."
- `AGENTS_MD.md` "Remove code made unused by your changes, but don't remove pre-existing dead code unless asked."
- `AGENTS_MD.md` "Do not refactor, clean up, reformat, rename, or otherwise improve unrelated work."
- `CLAUDE_MD.md:17` "Keep changes focused. Change only what is necessary to satisfy the user's request and produce a correct result."
- `CLAUDE_MD.md:11` "Do not make consequential assumptions silently."
- Scope lines stored in 16 of 24 plans: "Do not consider backward compatibility unless asked." (breezy-otter); "Scope is exactly these seven -- UIG-107, UIG-44, UIG-100, UIG-106, UIG-104, UIG-83, UIG-99. Nothing else." (valiant); "transactional is out of scope; note it rather than fix it." (cozy-truffle); "Pre-existing asymmetry, out of scope: ... Flagging, not fixing." (snug-hopping); "These are the only body changes in the whole repo. Everything else moves untouched." (migrate).
- "Delete dead code; remove whole features; no compatibility shims, aliases, or migrations" appears in 9 plans. "The user wants this feature wiped out completely -- no compatibility shims, no migrations" (buzzing-swinging-whale); "No aliases, no migration of config values." (parakeet); "Delete `content/docs/test.mdx` and `content/docs/new-testing.mdx`." (dreamy-quiche); "Delete `app/Http/Requests/Plugin/SyncPluginCategoriesRequest.php` (no other references)." (as-of-now); "DELETE: src/features/home/" (breezy-otter); "Delete the `// Vector store` and `// Embeddings` field blocks (lines 34-41)" (3-vector-store); "Unused `docs-grid.tsx`, `code-preview.tsx`, `cta-banner.tsx` and `DOC_LINKS` are deleted (they are dead...)" (warm-curry); deletes `stop_deadline`, `run_stop_timer`, `stop_recording_now`, the timer thread, `stopping_same_profile` (greedy-prism); "Delete `src/components/auth/*`, `src/features/billing/*`..." (check-cleaner-auth).
- "Prune orphaned imports every time a symbol is removed" appears in about 7 plans: as-of-now, buzzing, 3-vector-store, warm-curry, parakeet, playful-hoare, calm-willow.
- Over-deletion nuance in we-have-to-make-playful-hoare.md: "That was the right direction, but it went one step too far" (after deleting the `FeaturePage` abstraction); the plan then reintroduces exactly two shared primitives after measuring repetition and keeps "Everything else inline, deliberately".

## Docs writing and cleanup

### Prompt quotes

chunk-01 (~9 prompts, 6 projects)

- "WE WILL ONLY BE WORKING WITH @../uigraph-docs/ @../skills/ ONLY"
- "we have almost 300 lines of code.. we have to reduce it around 200...or less without losing contents"
- "we cant lose content.. we can remove nonsense contents"
- "## Post-Generation Validation has lots of changes we should not add bloated contentntes"
- "let's not show things that can't be done"
- "DELETE the readme entirely, work with other things"

chunk-02 (~21 prompts, 5 projects)

- "Check all the repo like agents, slack, cli ... Some of our docs are outdated we have to update the docs"
- "THE GOAL OF THE DOCS ARE FOR USERS WHO WILL USE THE PRODUCT, THE DOCS IS NOT FOR USERS/DEVELOPERS ABOUT CODE.."
- "AND DO NOOT FUCKING UPDATE DOCS.. thats not your task" (uig; logged as a scope correction, not a docs request)
- "We have to add a readme for how to use this.. keep it extremely simple and small"
- Sub-patterns in the report: docs are for end users, never leak implementation details; adding docs when not asked is a violation; docs-as-rules-file (`docs/button-rules.md` as single source of rules); doc files copied into a repo and linked, not linked across repos.

chunk-03 (~16 prompts, 4 projects)

- "The AISDK is basically a tool or a library for internal users. We don't have to explain anything there because it's just for internal users. But we have to explain a lot of things in the agents. Keep it extremely stupid simple."
- "Avoid doing this we try to link the docss first we dont have to explain everything from scratch because we are explaining them on our docs again"
- "...in @AGENTS.md explain how to develop this application... Keep it extremely short and concise. I fucking repeat again, keep it extremely short and concise."
- "I don't think so we need docs/github-app-onboarding.md"
- Report notes: AGENTS.md rewritten twice, rejected as "totally garbage"; docs must name source repos explicitly; README must not be trusted as evidence.

chunk-04 (~28 prompts, 5 projects)

- "we have to update our skills and docs based on current updates ofr last few days"
- "I cloned the skills .. needs to be updated too... \n also check the uigraph-agents tahts upated a lot"
- "use the docs skill and optimize the github app"
- "skills/uigraph/references/ci-cd-integration.md do not need to explain --verbose here"
- Report notes: recurring intent is docs and skills tracking the code; docs written from screenshots/mockups; troubleshooting docs page; UI errors linked to docs pages.

chunk-05 (~19 prompts, 6 projects)

- "can you write markdown files into @docs for like main-page.md, etc.. keep it very conisce and simple" (uigraph)
- "That designs.md should not be a garbage bullshit... should not include how to build... It should be extremely simple, extremely concise Extreme level of concise without losing any more details" (uigraph-web)
- "Do you see any kind of documentation mismatch with @uigraph-docs/ and rest of out products..? Do a read only review to find out all the mismatches and report to me. Do not make or change any file." (uigraph)
- "Migrate the entire repository from Docusaurus to Fumadocs using Next.js. I repeat: every single detail must be exactly the same. We don't want to change any route or any content." (uigraph-docs)
- "for these link claude.md -> agents.md AGENTS.md is the source of teh truth" (uigraph)

chunk-06 (~40 prompts, 5 projects)

- "We have to make our documents ( @maileditor-docs ) follow the original frontend site @Maileditor-frontend/"
- "lots of bloatware here and there. We have to clean them up. ... make them more concise and clear for end user and developers"
- "You can keep the screenshots from the dev; there's nothing wrong with that. However, the content will not be from the dev."
- "Show correct code snippets for each platform, eg: wordpress, next, vue, svelte, valinnajs etc."
- "We have to link it to the docs. We don't have to explain how that should be done"
- Report's intent line: "docs content accuracy, no dev-internal leakage, concise structure, per-platform pages, real screenshots."

chunk-07 (~30 prompts, 3 projects)

- "So if I have to set up, can I create a setup.md for the enterprise version? You can show which environment variables we need, what the URLs will be, etc. Keep it very simple"
- "create a markdown file across all the things we discussed.. ./REPORT.md"
- "Add a note here that this file should not be edited unless directly instructed. If the user does not explicitly say to edit it, the file should not be edited by an LLM."
- "I think we are clear enough for this.. can you help me to create a minimal simple PRD.md?"
- Named files demanded across the chunk: report.md, issues.md, setup.md, REPORT.md, checklist.md, GOAL.md, problem.md, PRD.md, SYNTAX.md, agents.md, chat-1.md. report.md was deleted once ("I deleted report.md fuck that") and rewritten from raw data.

chunk-08 (~9 prompts, 2 projects)

- "Please add an Agents.md and include these in your Cloud rules that do not run or verify using ESLint in the frontend repo."
- "For every step, we need to explain why it is required, how it works, and provide a link to our documentation for further information."
- "This description is totally nonsense and doesn't solve any problem. Link more documentation here about the selected method."
- "create a questions.md file here in this folder DO NOT USE ORDERED NUMBER LIST"
- "we have to add docs for our stock images"
- "...just note it down in NOTES.md."

chunk-09 (~6 prompts, 4 projects)

- "can you summarize the reaming changes in a lint.md file? at root"
- "src/lib/zstd-form/dictionaries/README.md add osething here explainng why this is soo importatnt"
- "can you fucking stop fucking updating the fukcing docs"
- "add a rules in this projegt agents.md taht never update docs uneless explcitly reuesstd"

duplicates run

- Theme 6, docs/README work including de-slopping: 148 prompts / 19 projects. Examples: "simplify the readme, The redmi includes a lot of slop and garbage and unnecessary bullshit.", "this looks like slop.. make it professional and clean".

### Stored rules and plans

- `as-of-now-our-witty-squid.md:84` "## E. Docs (concise edits)"
- `as-of-now-our-witty-squid.md:53` "Docblock touch-ups that now lie"
- `3-vector-store-and-logical-lake.md:22` "Delete the false feature bullet on line 16"
- `we-have-to-write-greedy-mitten.md:132` "Every factual claim traceable to the source files cited above -- no invented benchmarks, prices, or model names."
- `valiant-hugging-charm.md:87` "Add an explicit rule that README, CHANGELOG and similar files are never doc artifacts."
- `https-contentstack-com-docs-check-their-elegant-forest.md:70` "simple wording, no dashes/semicolons"
- `we-need-to-create-dreamy-quiche.md` "trim narrative to what a caller needs", "mark it as 'not currently returned'"
- buzzing-swinging-whale, luminous-rabbit, warm-curry, migrate, dreamy-quiche: docs/README updated as part of the same change.
- `we-have-to-write-greedy-mitten.md:146` "Confirm before publishing (I will write around these, not invent them)"
- `CLAUDE_MD.md:5` "Find facts yourself instead of asking the user."

## De-slop

### Prompt quotes

chunk-01 (~8 prompts, 3 projects)

- "DO NOT ADD BULLSHIT PILLS LIKE: AI Template Generator neer ever"
- "Seems like you totally copied every content from the image I shared earlier. Our content has to be better, even better. Just the UI has to be similar like them"
- "Make it professional. It has to be perfectly professional and perfect design... You don't have absolutely zero taste. Do what professionals do. Not make things by yourself."
- "But there is no relationship or meaning... Just make it good, I don't know how But make it good"

chunk-02 (~30 prompts, 7 projects)

- "You are literally creating totally garbage kind of model names... Choose good names, motherfucker. Do not use random characters."
- "I repeat again, we will not use any kind of placeholder name." (mlflow-explore)
- "in a simple English paragraph no technical garbage, no code, no anything"
- "Keep the code stupid simple. The code should be stupid simple and direct. Do not overcomplicate anything."
- Report's line: "plain language output, no technical garbage in plans/summaries, no placeholder/random generated names, no overkill behavior, reject AI-flavored verbosity."

chunk-03 (~10 prompts, 3 projects)

- "this is pure slop"
- "this looks like entire fucking slop.. fuck yoy..  I SAID MAKE IT BETTER"
- "...we can make it less screens and less ai slop"
- "doesn't fit our design system cringe"
- Other asks logged: "Avoid using slop everywhere", "the primary color looks cringe", "It looks like slightly cringe, especially the card thing", "don't make the title/subtitle cringe/smaller"

chunk-04 (~20 prompts, 4 projects)

- "[Image #1] Make this page better. Requirements: - Centerd SIngle Column Layout - No repo acess needed - No cringe ui - Must look good"
- "make it not slop.. make it professional"
- "the cardish ui doens't look great be creative make it feel smooth and native without bloated ai slop"
- "That looks very cringe. That check thing is very cringe. keep it simple and very slightly animatedbe professinal"
- "(avoid ai slop and cringe)"

chunk-05 (~15 prompts, 5 projects)

- "This kind of levels looks like pure garbage AI slop." (uigraph-ui)
- "The biggest problem is our entire landing page looks extremely level of AI slop... We have to make it better." (uigraph)
- "This looks really AI-slopped." (uigraph, about section titles)
- "FOllow @DESIGN.md .. avoid generic ai slop..." (uigraph-web)
- "As of now our blog pages looks like totally slop and extremely unusable." (uigraph-web)

chunk-06 (~16 prompts, 5 projects)

- "This seems like bloated garbage; completely garbage AI slop"
- "I don't want garbage slop. I don't want jargon."
- "stop giving me unnessary garbage slop"
- "This seems to be extremely implementation jargon. I do not want to read this. Please make it less sloppy."
- "Can you ignore all the jargon, unnecessary garbage, and nonsense questions and make the plan again?"
- /unslop invoked twice in this chunk.

chunk-07 (~30 prompts, 4 projects)

- "bro you are giving me slop.. what was my quesion?"
- "Again, you are giving me that slop. Keep it extremely concise; it must be at an extreme level of conciseness. I don't want to get angry again about this."
- "It has to be very minimal. As of now, it is just pure slop."
- "I DO NOT LIKE SLOP LIKE THIS I DO NOT LIKE SHITY LIKE THIS no congiuration.."
- "keep it short and small, I cant read 10000 lines slop"
- Report note: 24 /unslop invocations in this chunk, plus demands like "must use the unslop skill before doing it".

chunk-08 (~22 prompts, 4 projects)

- "[Image #2] this is extreme levelof slop, extrmeme level of bloat /unslop"
- "What is the address bar man? What is this? This is just pure slop!"
- "its not enough.. cleanup more slop"
- "[Image #7] this looks like slop.. make it professional and clean"
- "this looks really disgusting.. this slop is eveyrwhere it sucks"
- "window inside another window. what kinda slop is this?"
- Report note: /unslop and /unslop-design appear in 5 separate sessions across 4 projects.

duplicates and wildcard runs

- "slop" in 35 prompts / 9 projects. Examples: "no slop", "make it not slop.. make it professional", "our entire landing page looks extremely level of AI slop".
- Theme 14, "I don't want X" rejection of an approach: 36 prompts / 11 projects. Examples: "This is more slop; this is really slop. I do not want any kind of window.", "I said I don't want that!"
- Custom slash commands: /unslop 36 (23 as a one-word prompt), /stupid-simple-code 2. "The most-used self-authored commands are not about code quality checks but about the agent's tone, simplicity, and behavior."

### Stored style rules

- `CHATGPT.md:1` "Be as concise as possible. Answer only the exact question asked, using the minimum information required, and stop as soon as the answer is complete."
- `CHATGPT.md:3` "Treat anything beyond the minimum direct answer as incorrect unless I explicitly ask for more detail."
- `CHATGPT.md:5` "Never use em dashes. Avoid regular dashes where possible."
- `CHATGPT.md:3` "Use straight apostrophes and quotation marks, not curly ones."
- `unslop/SKILL.md:52` "Avoid em dashes entirely. Use periods or commas only (no parentheses, no en dashes, no hyphen-as-dash substitutes)."
- `unslop/SKILL.md:43` "AI vocabulary... Replace with plain words."
- `unslop-design/SKILL.md` bans pills/badges above headings, repeated patterns, cards-in-cards, unbalanced columns, numbering as decoration, fabricated product UI, hand-drawn brand logos.
- `~/.claude/settings.json` (symlink to `~/.dotfiles/config/ai/claude.json`): `"outputStyle": "Consice"` (sic).
- `https-developers-contentstack-com-we-hav-delightful-puffin.md:75` "Remove the author avatar/role block from cards ... it's pure repeated noise and it's what makes the current grid feel like slop."
- `CLAUDE_MD.md:43-45` "Lead with the most important information", "Keep only useful details."

## Model behavior that triggers these asks

### Correction classes from short prompts

| Class | Count | Projects | Examples |
|---|---|---|---|
| "didn't do what I asked / ignored instruction" | 150 | 19 | "did i said to write code?", "what was the fucking requirment?", "WRITE THE TESTS EXACALY HOW I SAID NOTHING ELSE", "Did I say to create anything? Did I say to restore anything?", "You completely ignored that it is about Auto Layout." |
| "did something extra / scope creep" | 70 | 13 | "why the fuck you removed the hr/br like thing?", "nobody asked to add recommended", "AND DO NOOT FUCKING UPDATE DOCS.. thats not your task", "JUST RUN make e2e NOTHING ELSE", "did i ever said to drop pull req from the artifact gen?" |
| "claimed done but broken / not verified" | 45 | 15 | "it's saying wrote ok.. but actually not", "No, you haven't checked it.", "you lied to me?", "ai text updater is indeed working.. why are you lying?", "so why you havent said its not fixed?" |
| "too much output / verbose / slop" | 13 | 5 | "keep it short and small, I cant read 10000 lines slop", "I do not want an entire novel.", "Give me the fucking summary motherfucker", "Give me a concise output." |
| "wrong file/location" | 11 | 5 | "i said seed.py not seed_mlflow", "the blank video should be under /public/blank-video.mp4", "It should be inside resouces" |
| "still broken" | 61 | 15 | "still not wokring", "[Image #2] I'm still seeing the MV", "I am still facing the same problem.", "it looooks like the exact same garbage" |
| "undo/revert demand" | 32 | 13 | "revert whatever you did", "REVERT IMMMEIDIENTELK6", "DO NOT USE GIT.. revert manually", "revert the garge you did last time" |
| "frustration venting" | 354 | 26 | "stop fucking wasting time motherufkcer", "This is extreme level of garbage.", "you are a slop", "This is the most garbage design system I have ever seen." |
| "confirmation/continue" (not a correction) | 318 | 30 | "continue", "all done?", "sure? can you double check", "implement", "go ahed" |

### Top 10 recurring correction patterns

From the corrections run (trigger, reaction, count, with formula counts in parentheses):

1. Agent does work that was never requested, then interrogation: "Did I say to...?", "What I said?", "what was my requirment?" -- 150 lines / 19 projects (recall formulas: "I said/asked" 332, "did i say/ask" 82, "never said" 55).
2. Agent adds or changes beyond scope: "what the fuck is this?", "nobody asked", "that's not your task" -- 70 / 13 (plus 51 lines of "do exactly/only what I said" across 11 projects).
3. Fix reportedly done but still broken: "still not wokring", "same garbage", "again" -- 61 / 15 ("still" 68, "not working" 34, "broken" 102, "again" 155).
4. Agent didn't actually verify: "you haven't checked it", "you lied", "did you verify the ui?" -- 45 / 15 (plus 103 verification-demand lines across 14 projects).
5. Change botched the codebase, immediate revert demand -- 32 / 13 (revert/undo formulas 79 lines across 14 projects).
6. Accumulated fury, profanity and "garbage/slop" -- 354 / 26 (609 lines contain fuck-family profanity, 24 projects).
7. Too much output or explanation: "keep it short", "I can't read 10000 lines slop", "I do not want an entire novel" -- ~65 / 12 on brevity formulas, 351 lines on slop/garbage across 23 projects.
8. Wrong method, file, or tool: "NEVER USE PYTHON", "i said seed.py not seed_mlflow", "use pnpm" -- ~45 / 12.
9. Question dodged: "thats not an answer", "That was not my question... Yes or no?" -- 19 / 9.
10. Trust collapse: "you lied to me?", "it's saying wrote ok.. but actually not" -- ~15 / 7.

### Transcript phrase counts

From 575 transcript files (2.0 GiB), 6,664 user-text lines, 343 top-level sessions:

| Phrase | Occurrences | Files |
|---|---|---|
| I said | 446 | 60 |
| stop | 406 | 78 |
| revert | 367 | 54 |
| again | 756 | 115 |
| I don't care | 130 | 26 |
| just do | 119 | 22 |
| undo | 102 | 27 |
| I asked | 61 | 18 |
| what the fuck | 65 | 18 |
| not what I | 49 | 12 |
| I only | 33 | 19 |
| still not | 13 | 6 |

- Sessions with at least one corrective phrase: 119 / 341 = 34.9%. High-signal only (excluding stop, again, just do): 90 / 341 = 26.4%.
- `I said` appears in 60 files across 10 distinct project dirs; `revert` 54 files / 9 projects; the same project dirs recur: uigraph/uig, wm/maileditor and frontend, oiper-desktop, dotfiles.

### Correction classes from transcripts

1. Scope creep, did more than asked: "Bro, I just said to fix this diagram, absolutely nothing else. So why did you fucking fuck ten files?"; "I asked to copy from the mockup not add another layer of your garbage"
2. Wrong target or instruction drift: "That's not what I said to do. I never said you to do that... I only said you will write the files."; "That's not what I want. I don't want garbage slop. I don't want jargon."
3. Unauthorized edits to untouched files, must undo: "I am asking why you changed that file. What problem were you trying to fix?"; "color picker is perfect, don't touch it; focus on layout broken pieces"
4. Ignored explicit prior constraint: "I said not to..." and "I said no" recur across 9+ files
5. Regressions, breaking what worked: "You broke every layout. You broke everything. I just asked for the sizing. Just the sizing."; "close but still not perfect your version is bloated.. like why i need text options for table?"
6. Over-engineering, slop, bloat: "Whatever design philosophy you added about the attributes, all of them are totally garbage."; "I explicitly did not ask for any new feature. What are the new features you added?"
7. Not converging, repeated loop: "Just fucking remove it. I repeat again, remove it. Remove it entirely."; "None of them actually solved my problem. My question is: why did you do that?"
8. Stop commands, guarding live processes: "do not run next dev/build, don't touch any dev server"; "Do not preserve my current changes and stop reverting..."

### Specialist repeat signals

- Comment cleanup demand: 25 lines / 8 projects, triggered by the agent writing comments: "remove comments", "NO FUCKING COMMEMENTS", "Delete all the comments you wrote", "Still I see some comment".
- Don't run or build: 26 lines / 9 projects: "DO NOT RUN ANTTHING>>> RUNNING IS NOT YOUR TASK", "I never said to run the test... do not run the test", "You should not run this application."
- Method prohibition: 11-34 lines / 6-11 projects: "NEVER USE PYTHON", "DO NOT USE useEFFECT", "use you rfucking tool not a fucking shell command", "I said to use a reliable lib not local hoook".
- Don't decide on your own: "Did I ever say to decide you by your own?", "do what i said .. DO NOT TRY TO BE SMART IN ANY FUCIIG WAY", "That's not a issue. I never said you to be smart."
- Just answer the question: "thats not an answer", "That was not my question. My question was: does that same behavior exist in the main timer? Yes or no?"
- "I don't care" shutdowns: 64-71 lines / 13 projects, triggered by over-explaining and hedging: "I don't care any of those f**king technical information. Where is that in the UI?", "I don't care. I don't give a fuck about that. Just copy the original button."
- Explicit bans, 72 prompts / 15 projects: "DO NOT USE GIT.. revert manually", "NEVER USE PYTHON", "DO NOT WRITE TESTS", "DO NOT use em dash".
- Reversion loop: 28 prompts say "I reverted"; 68 prompts use revert/undo; 81 exact non-command re-sends inside the same session; 4 prompts repeat the entire plan-copy instruction verbatim.
- Same cleanup re-requested: "cleanup all onboarding tables" repeated across 4 separate sessions (uig), the same cleanup re-requested at least 5 times.
- Profanity is mid-session, not an exit: 620 prompts (9.5%) contain fuck-family profanity, 134 sessions; the mean prompts remaining after the first profanity is 23.9; median position is 35% into the session; 94% of profane prompts are followed by more work.
- "just" appears in 607 prompts (9.3%); "only" in 263; negations in 30% of prompts.
- Repo hygiene after deletions is a stored plan instruction, not a prompt quote: "prune orphaned imports every time a symbol is removed" (about 7 plans).

## Method and sources

- Prompts: `~/.claude/history.jsonl`, 6,537 prompts, 751 sessions, 51 cwds, Aug 1 to Sep 25 2026. Normalized to `prompts.jsonl`; 5,590 text prompts used for counts after removing paste and image markers. 164 pastes totaled 27,752 declared lines; 784 prompts carried `[Image #N]` (12.0% of the corpus).
- Transcripts: 575 `.jsonl` files, 2.0 GiB, 343 top-level sessions, 6,664 user-text lines. Counts include user-written recaps that quote earlier corrections, so they are slightly inflated.
- Plans and stored files: 24 plan files, 270,824 bytes / 3,897 lines, plus `CLAUDE_MD.md`, `AGENTS_MD.md`, `CHATGPT.md`, `settings.json`, and the skill files. `CLAUDE_MD.md` and `AGENTS_MD.md` share most content; `~/.claude/CLAUDE.md` is a symlink to `~/.agents/skills/CLAUDE_MD.md`, and `~/.claude/settings.json` symlinks to `~/.dotfiles/config/ai/claude.json`.
- Mining: 20 parallel agents, 9 of them full-history chunk readers (each read every prompt line in its range and counted by intent), plus runs for duplicates and ngrams, corrections, leading verbs, plans and config corpus, transcripts, weekly trends, session lifecycle, reset phrases, wildcard meta-analysis, and regex validation.
- Caveats: intent counts overlap (one prompt can reject output and re-assert scope); regex precision varies (simplify 75%, docs 95%, scope discipline 95%); uigraph subfolders count as separate cwds, which inflates that family's project spread; duplicate prompts exist in the corpus; timestamps are UTC as recorded.

## Mining reports

Temp directory `claude-prompt-mining`:

- `recurring-patterns.md` - ranked inventory of all patterns and the wacky findings.
- `agents/chunk-01.md` through `agents/chunk-09.md` - full-history readers.
- `agents/dups-ngrams.md` - 123 duplicate clusters and top ngrams.
- `agents/corrections.md` - reaction classes, formulas, top 10 correction patterns.
- `agents/plans-corpus.md` - stored rules from plans, memory, config, and skills.
- `agents/transcripts.md` - phrase counts and correction classes from session transcripts.
- `agents/trends.md` - weekly shares and trend classification.
- `agents/wildcard.md` - meta-analysis over the whole corpus.
- `agents/taxonomy-validation.md` - regex vs actual prompt sampling and precision.
- `agents/session-lifecycle.md`, `agents/reset-recovery.md`, `agents/verbs.md` - session and corpus mechanics.

## Related files

- `~/.agents/skills/unslop/SKILL.md` (8,123 bytes) - existing de-slop writing catalog.
- `~/.agents/skills/unslop-design/SKILL.md` (1,354 bytes) - existing visual de-slop rules.
- `~/.agents/skills/CLAUDE_MD.md` (3,917 bytes, symlinked as `~/.claude/CLAUDE.md`) and `~/.agents/skills/AGENTS_MD.md` (3,137 bytes) - standing rules quoted above.
- `~/.agents/skills/CHATGPT.md` (1,669 bytes) - brevity, plain ASCII, no em dashes.
- `~/.claude/plans/` - 24 plan files quoted above.
- `~/.claude/history.jsonl` - the prompt log behind all counts.