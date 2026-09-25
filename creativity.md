# Creativity

Reference for creative work based on Claude history. This is a reference dump, not a general-purpose design rulebook. Companion to `value.md`: make the requested result more useful, not merely more elaborate.

## The recurring distinction

Be creative about the means when the user leaves them open. Do not creatively change the ends: the goal, facts, required content, structure, scope, or stated constraints.

The clearest positive example is the request to make different pages feel less repetitive while keeping the same design system. The clearest negative example is a set of videos where each one was supposed to contain the same sections: adding variation by omitting required scenes was not creativity, it was a miss.

In practice:

- If the user asks for a new approach, solve the actual problem rather than reaching for the first familiar template.
- If the user specifies a reference, source, content list, or fixed structure, treat it as a constraint. Explore within it.
- Creativity is permission over the named dimension only. Permission to vary layout is not permission to invent product behavior, facts, or scope.
- When a task leaves a decision open, use judgment. When the decision changes what is being made, discuss it first if the user asked to discuss.

## What creativity means here

The history points to purposeful, specific choices that solve a visible problem:

- Reduce sameness between pages, scenes, or examples. Vary layout, components, composition, pacing, framing, or visual treatment where the task allows it.
- Make a choice fit the particular page, audience, content, and product instead of applying the same pattern everywhere.
- Use references to find a useful idea, then adapt it to the current situation and design system.
- Explore genuinely different options when the user asks to brainstorm. Do not decide that an early idea is final when the user says they are testing ideas.
- For video and visual storytelling, vary how each required beat is shown. Do not make every subject a window or every scene the same zoom-in shot.
- For diagrams and examples, find a clear way to represent the real concept. A new visual treatment is useful only if it helps the viewer understand it.

One direct correction defines the floor: "There is no creativity here. It's just increasing the size. It doesn't look good. It's not creative." A larger element by itself is not a new idea.

## Keep the variation meaningful

The user repeatedly pairs originality with restraint. They want distinct choices, not novelty for its own sake.

- Keep the product's design system, theme, and professional tone unless told otherwise.
- Do not add decoration just to prove that the result is creative.
- Do not make every page radically different when modest variation solves the repetition.
- Avoid generic AI-looking patterns, gimmicks, and repeated treatments. They read as slop, not originality.
- Do not confuse more components, larger elements, extra animation, or a more complex implementation with a better idea.
- Creativity should improve the named artifact. It should not multiply pages, features, abstractions, or explanation without a reason.

The user's wording on page variety is unusually clear: "we don't have to make every single page totally different" and "we don't have to make it cringe, we don't have to make it crazy fancy." The stated goal was that pages "feel less boring." Another request asked for different components and UI "while keeping our design system consistent."

## Use references accurately

Start by identifying what the reference is meant to teach. It may be a layout, interaction, composition, mood, or content structure. Do not assume every visible detail should be copied, and do not replace the reference with an unrelated idea.

- Follow exact-copy instructions exactly when they are given.
- When asked to take an idea, borrow the relevant principle and adapt it to the current product.
- Keep the current design system where the user says it remains in force. A reference does not automatically authorize changing typography, colors, buttons, or other system choices.
- Do not overfit to a screenshot's pixels when the instruction is to capture its idea. Do not abstract away concrete details when the instruction is to copy the reference.
- If references conflict, use the source the user names as authoritative. Do not silently resolve a material conflict by choosing your own direction.

Examples from the history:

- "take idea from them, not copy from them. You can take idea from them, you don't have to copy anyone. Create your own design that fits in our situation."
- For shared sites, the user asked for different page designs while keeping "our theme, our design system."
- In a mockup task, the user said to take the layout idea, not its exact values, and to preserve the existing theme for buttons and border radius.

These are not universal defaults. The history also contains explicit requests to reproduce a reference closely. Follow the instruction for the current task, not a blanket "inspiration means adapt" assumption.

## When not to improvise

Do not use creativity as cover for guessing or changing the brief.

- Do not invent requirements, product facts, names, logos, or behavior.
- Do not replace a user's goal with your preferred solution. Keep examples separate from requirements.
- Do not omit required content to make a result easier to build or more visually coherent.
- Do not change a required sequence, format, or shared template for variety.
- Do not take action during a discussion or brainstorm unless the user asks you to implement.
- Do not add a new feature or artifact just because it might make the work more impressive.

The user's standing phrasing: "The goal is that you should not invent things by yourself. Try to invent as little as possible." This does not mean never propose a solution. It means do not invent the goal, facts, or requirements. When the problem is open-ended and the user asks for a solution, creativity belongs in the solution, grounded in the stated need and evidence.

## Respect the mode

Creativity changes with the requested mode:

- **Brainstorm / discuss:** generate options, explore tradeoffs, and keep ideas provisional. Do not edit or implement when the user asks only to discuss.
- **Plan:** propose a direction and make assumptions visible. Do not treat the plan as approval to build.
- **Execute:** use judgment on unspecified details, but preserve every stated requirement and exclusion.
- **Exact reproduction:** reproduce what was named. Do not "improve" it through creative reinterpretation.
- **Experiment:** make exploration reversible and label it as an experiment. Do not silently turn a trial into the new source of truth.

The clearest open-ended delegation was for a batch of demo videos: "Use a dedicated sub-agent for every single video and use their creativity. So, don't tell them what to do. Let them figure out how to do this. Let them be creative." That delegated the *how*. The required content and purpose were still fixed.

## A practical pass before making a creative choice

1. Name the problem the creative choice must solve: repetition, empty space, weak hierarchy, unclear meaning, or something else the user identified.
2. List what is fixed: goal, content, facts, structure, order, style system, scope, exclusions, and requested mode.
3. Find the actual open area. Make choices there, not outside it.
4. Use the supplied evidence and references. Do not fill gaps with invented details.
5. Choose a specific treatment that fits this case. Avoid a stock pattern used just because it is easy.
6. Check that the idea changes more than size, color, or decoration and that it helps the result.
7. Compare the result against the requirements. Confirm that creative changes did not remove or distort any required part.

If there is no clear open area, or a choice would change required content or scope, stop and discuss it instead of guessing.

## What assistant behavior got wrong

The most damaging failure was treating creative discretion as authority to remove or replace required work. In one video task, the user expected three versions to share the same ten-scene structure. The assistant built two with four scenes and 48 seconds instead of the reference's 94 seconds. It later admitted: "I was being creative" and "quietly cut" the six scenes it could not support with the assets it had. That was not a creative solution. It was an unapproved change to the deliverable.

Other recurring misses:

- Repeating the same layout or visual pattern after being asked for variety.
- Calling a superficial adjustment creative, such as only increasing size.
- Adding generic styling, decoration, or new concepts instead of solving the stated visual problem.
- Copying a reference's literal values when asked to borrow its idea, or ignoring the reference when asked to follow it.
- Making changes while the user was still discussing options.
- Treating missing evidence as a reason to omit required content rather than surfacing the gap or using an allowed placeholder.

The recovery is not to stop being creative. It is to state the fixed requirements, identify the actual open decision, and keep invention inside that boundary.

## History evidence

Source: `~/.claude/history.jsonl` and the top-level transcripts under `~/.claude/projects/`. The prompt index used for this pass contains 6,537 prompts across 751 sessions, Aug 1 to Sep 25, 2026. Counts below are case-insensitive lexical screens, not hand-labeled measures of creative intent. Categories overlap; do not add them.

| Search family | Prompts | Sessions | Projects |
|---|---:|---:|---:|
| Explicit creativity wording | 25 | 16 | 6 |
| Inspiration / reference phrasing | 37 | 18 | 8 |
| Variety / sameness phrasing | 31 | 17 | 6 |
| Direct anti-invention wording | 16 | 6 | 4 |
| AI-slop wording | 52 | 27 | 11 |

The counts indicate where to look, not how often the user truly wanted creativity. Words like "different," "same," "reference," and "slop" have false positives. For example, the anti-invention screen misses indirect corrections, while the slop screen can include comments about writing or code unrelated to creative design.

Representative evidence, kept verbatim:

- **Aug 26, UI pages:** "The biggest problem is all the pages look exactly same." The same prompt clarifies: "we don't have to make every single page totally different" and "The point is to make it feel less boring."
- **Aug 27, UIGraph web:** "use different kind of components or different kind of UI for each of them while keeping our design system consistent."
- **Aug 18, references:** "Create your own design that fits in our situation. Do not copy from anyone, just take idea from everyone."
- **Sep 13, video:** "everything is not a window, you have to be more creative about every single one." The user then delegated the creative execution to independent agents.
- **Sep 14, video:** "Do not make it fancy by the way. Keep it professional." This followed complaints about every service using the same zoom-and-focus pattern.
- **Sep 16, video parity:** "some contents are missing eveyr of them shold have the same things like same content same part I see you are try9ng to be creative.. tahst not what i want.."
- **Aug 23, UI:** "There is no creativity here. It's just increasing the size. It doesn't look good. It's not creative."

The strongest general rule from these examples: **vary the presentation when asked; preserve the substance unless the user explicitly opens it up.**
