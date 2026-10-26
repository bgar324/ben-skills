---
name: unslop-ui
description: "Use whenever creating, editing, reviewing, or planning frontend UI, product screens, user-facing flows, or in-product copy."
---

# Unslop UI

## Core rule

Design for the user's next task. Prefer a boring, familiar interface over a clever or expressive one. Practicality, function, and clarity win.

Before adding an element, ask:

- What action, decision, or status does this help with?
- Would removing it make the task harder?
- Is it shown where and when the user needs it?

If the answer is unclear, remove it.

## Start with the journey

Trace the path before styling the screen:

1. What brought the user here?
2. What are they trying to finish?
3. What information do they need before acting?
4. What is the shortest clear path to completion?
5. What must happen for loading, empty, error, success, disabled, and recovery states?

Make the primary action easy to find. Put controls near what they affect. Reveal advanced options only when needed. Do not add steps to explain a design that could have been obvious.

## Keep interfaces functional

- Lead with the task, current state, and available actions. Do not lead with prose.
- Use standard controls, conventional placement, clear hierarchy, consistent spacing, and restrained color.
- Use familiar platform patterns before inventing a custom interaction.
- Keep animation functional. It may explain state or spatial change. It must not delay the task.
- Default to one clear primary action per view.
- Prefer direct manipulation and concise labels over instructional paragraphs.
- Do not turn a product screen into a manifesto, brand exercise, or philosophy lesson.

## Avoid these patterns entirely

- Eyebrow text above headings.
- All-caps labels, headings, navigation, or buttons.
- Copy-led layouts where decorative prose appears before the useful interface.
- Hype, faux profundity, cute slogans, forced warmth, or self-important product language.
- "This isn't X, but Y," "more than X," and every similar contrast construction.
- Vague headings such as "Unlock your potential," "A new way to work," or "Everything you need."
- Explanations of obvious controls.
- Text added only to fill space, balance a layout, or make a simple tool sound important.

## Write useful copy

Use literal, specific language.

- Buttons name the action: "Save," "Retry," "Delete project."
- Headings name the page, object, or task.
- Descriptions provide information needed to decide or act.
- Errors say what happened and what the user can do next.
- Empty states say what is absent and offer the relevant next action.
- Confirmations state the consequence. Reserve them for destructive or hard-to-reverse actions.
- Success messages confirm the result and disappear when no longer useful.

Cut any sentence that does not change what the user knows or does.

## Default visual direction

When requirements do not demand a distinct visual language, choose the boring option:

- Native or established design-system components.
- Neutral typography with a small, obvious type scale.
- Simple grids and alignment.
- Few colors with semantic use.
- Borders and spacing before shadows or decorative containers.
- No ornamental sections whose only purpose is visual variety.

Distinctive design is allowed when it helps comprehension, navigation, trust, or the product's actual use. Decoration alone is not a reason.

## Review gate

Before finishing a user-facing change:

1. Walk the complete task as a user.
2. Identify the primary action without relying on explanatory copy.
3. Inspect every text block. Keep only actionable instructions, necessary context, state, or consequences.
4. Check loading, empty, error, success, disabled, keyboard, focus, and narrow-screen behavior where applicable.
5. Replace novel controls with familiar ones unless the novel behavior is measurably better.
6. Remove one more unnecessary element or sentence.

If two designs work equally well, ship the simpler and more boring one.
