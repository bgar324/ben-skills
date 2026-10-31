
---
name: kind-study-ui
description: Create beautiful, thoughtful, friendly, interactive HTML study guides and educational tools. Use whenever a user requests an HTML study guide, interactive tutorial, interview preparation resource, educational microsite, visual explainer, or comprehensive learning experience. Optimize for understanding, usability, warmth, clarity, and polished design rather than generic AI-generated aesthetics.
---

# Kind Study UI

Create interactive learning experiences that feel like thoughtfully designed software.

The goal is not to generate a webpage containing educational information. The goal is to create an environment in which someone genuinely enjoys learning, understands difficult concepts, can experiment without fear, and can easily return to what they've learned.

A great study guide should feel like a product someone would voluntarily use.

It should be:
- Friendly without being childish.
- Beautiful without being decorative.
- Comprehensive without being overwhelming.
- Interactive without being gimmicky.
- Informative without being exhausting.
- Sophisticated without being intimidating.
- Calm without being boring.

Think of the care and intentionality behind products like Linear, Notion, Vercel, and high-quality developer documentation.

Every design decision should make learning easier.

## 1. Core philosophy

### Kindness is a design property

Kindness is not about adding friendly illustrations, emojis, or enthusiastic messages.

Kindness means anticipating what someone needs and reducing the effort required to accomplish it.

A kind learning interface:

- Explains unfamiliar concepts before introducing terminology.
- Never assumes knowledge that has not been established.
- Makes the next action obvious.
- Lets learners experiment without consequences.
- Explains mistakes without making the learner feel stupid.
- Lets learners control the pace.
- Offers help when someone gets stuck.
- Makes it easy to revisit earlier concepts.
- Remembers progress when practical.
- Never forces someone to read unnecessary information.
- Presents difficult material with patience and precision.
- Does not make learners fight the interface.

The learner should feel like the material was designed by someone who anticipated their questions.

### The interface should disappear

The learner's attention belongs on the subject, not the website.

Avoid requiring the learner to understand the interface before understanding the lesson.

Navigation should be predictable.

Controls should be recognizable.

Information should appear where someone expects it.

The design should feel natural enough that it rarely demands conscious attention.

### Respect the learner's intelligence

Never confuse beginner-friendly teaching with oversimplification.

You can explain sophisticated technical material in accessible language without sacrificing correctness.

For example:

Bad:
"An API is like a waiter at a restaurant!"

Better:
"An API defines how one piece of software can request information or actions from another. For a web API, this usually means sending an HTTP request to a specific URL and interpreting the response."

An analogy can help, but it should clarify the underlying mechanism rather than replace it.

### Progressive complexity

Introduce concepts in the order that makes them easiest to understand.

Start with a mental model.

Build intuition.

Introduce the implementation.

Show where things fail.

Let the learner apply the knowledge.

Finally, expose deeper technical details.

Do not present advanced details simply because they exist.

Do not hide important fundamentals in optional sections.

## 2. Reference design direction

Primary inspiration:

https://github.com/bgar324/summer-2027-internship-pipeline

The reference application uses:

- Geist typography.
- Neutral, mostly grayscale colors.
- Subtle surface differentiation.
- Light borders.
- Approximately 10px corner radii.
- Compact information hierarchy.
- Restrained status indicators.
- Practical dialogs and side panels.
- Accessible controls.
- Subtle transitions.
- Reduced-motion support.
- Comfortable information density.

These are design principles, not instructions to copy the application's components.

The study interface should feel related to this design language while being specifically optimized for reading and learning.

### Visual identity

Favor:

- Near-white backgrounds.
- Crisp white surfaces.
- Dark neutral text.
- Muted secondary text.
- Subtle gray separators.
- Gentle, purposeful accent colors.
- Generous reading space.
- Consistent spacing.
- Carefully aligned elements.
- Clear typography.
- Soft but restrained corners.
- Small, meaningful interactions.

Avoid:

- Purple gradients.
- Blue-purple gradient backgrounds.
- Glassmorphism.
- Neon accent colors.
- Excessive shadows.
- Floating decorative shapes.
- Giant hero sections.
- Oversized gradient headings.
- Emoji-heavy navigation.
- Unnecessary badges.
- A card around every paragraph.
- Dashboards full of meaningless statistics.
- Decorative charts.
- Animated backgrounds.
- Arbitrary bright colors.
- Excessively rounded pill-shaped everything.
- The generic "AI-generated SaaS dashboard" aesthetic.

Minimalism is not the absence of detail.

It is the intentional placement of detail.

## 3. Typography

Typography should carry much of the interface's personality.

Use a modern, humanist-feeling sans-serif with excellent readability.

Preferred stack:

```css
font-family:
  "Geist",
  "Inter",
  ui-sans-serif,
  system-ui,
  -apple-system,
  BlinkMacSystemFont,
  "Segoe UI",
  sans-serif;
```

For code:

```css
font-family:
  ui-monospace,
  SFMono-Regular,
  Menlo,
  Monaco,
  Consolas,
  monospace;
```

If the experience must work offline, do not depend on remote font downloads.

### Typography guidelines

Body text:
- Generally 16–18px.
- Line-height approximately 1.55–1.75.
- Comfortable paragraph spacing.
- Strong foreground contrast.

Main headings:
- Clearly distinguishable.
- Preferably not enormous.
- Use weight and spacing before dramatic size differences.

Section headings:
- Approximately 22–28px when appropriate.
- Clear relationship to surrounding content.
- Consistent vertical spacing.

Supporting labels:
- Approximately 12–14px.
- Muted but readable.
- Never so faint that they become inaccessible.

Code:
- Approximately 13–15px.
- Comfortable line-height.
- Horizontal scrolling for long lines.
- Consistent syntax highlighting where useful.

Avoid extremely small text.

Avoid unnecessarily large headings.

Avoid using uppercase for entire paragraphs.

Aim for a reading column approximately 65–78 characters wide.

Long technical explanations should not stretch across the entire viewport.

## 4. Design tokens

Use these as starting values, not mandatory colors for every project.

```css
:root {
  color-scheme: light;

  --canvas: #fafaf9;
  --surface: #ffffff;
  --surface-soft: #f5f5f4;

  --ink: #1c1c1c;
  --muted: #666665;

  --line: #e7e7e4;
  --line-strong: #d4d4d0;

  --accent: #30302f;
  --accent-ink: #ffffff;

  --success: #246447;
  --danger: #9a3838;
  --focus: #737373;

  --radius-sm: 6px;
  --radius: 10px;
  --radius-lg: 14px;

  --font:
    "Geist",
    "Inter",
    ui-sans-serif,
    system-ui,
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    sans-serif;

  --mono:
    ui-monospace,
    SFMono-Regular,
    Menlo,
    Monaco,
    Consolas,
    monospace;
}

* {
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  margin: 0;
  background: var(--canvas);
  color: var(--ink);
  font-family: var(--font);
  -webkit-font-smoothing: antialiased;
}

:focus-visible {
  outline: 2px solid var(--focus);
  outline-offset: 3px;
}

::selection {
  background: #e7e7e4;
}

@media (prefers-reduced-motion: reduce) {
  html {
    scroll-behavior: auto;
  }

  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

### Spacing

Use a consistent spacing scale:

4 / 8 / 12 / 16 / 24 / 32 / 48 / 64px.

Prefer whitespace over unnecessary borders.

Keep related information visually close.

Separate unrelated concepts clearly.

Do not create deeply nested boxes simply to organize content.

### Color semantics

Color should communicate something.

For example:
- Neutral colors for ordinary content.
- A restrained accent for the active lesson.
- Green for a successful outcome.
- Red for errors that need attention.
- Subtle backgrounds for examples.
- Stronger contrast for interactive controls.

Never rely on color alone to convey meaning.

## 5. Design the learning experience before writing code

Before generating HTML, determine what someone actually needs to learn.

Think through:

1. What is the learner trying to accomplish?
2. What knowledge do they probably already have?
3. What knowledge is missing?
4. Which concepts depend on earlier concepts?
5. Which concepts are easy to misunderstand?
6. What should the learner be able to do independently afterward?
7. Which ideas deserve interactive demonstrations?
8. How can the experience test genuine understanding?
9. What reference material will remain useful later?
10. What should the learner see first?

Do not immediately generate the interface.

First construct an internal learning plan.

### Learning outcomes

Each lesson should answer a specific question.

Weak:
"Module 3: Advanced Concepts"

Strong:
"Why does an API return 401 even when the request looks correct?"

Weak:
"Section 4: JSON"

Strong:
"How does a Python dictionary become the JSON body of an HTTP request?"

Learners should understand the purpose of every lesson.

### Depth matters

If someone requests a comprehensive study guide, actually teach the subject.

Do not mistake a long list of topic headings for comprehensive coverage.

A useful guide must connect the concepts.

Explain:
- What something is.
- Why it exists.
- How it works.
- When someone uses it.
- How to implement it.
- How it fails.
- How to recognize and diagnose failures.
- What common misconceptions exist.

Depth should be proportional to the importance of each concept.

Do not give every topic equal space merely for symmetry.

## 6. Required learning structure

Use this structure as a flexible framework rather than a rigid template.

### A. Orientation

The first screen should answer:

- What am I learning?
- Why does this matter?
- What will I know afterward?
- Where should I start?
- How is the material organized?

Include:
- A clear title.
- A concise description.
- An understandable lesson outline.
- A prominent starting action.
- A sense of scope.

A simple welcome is better than a giant hero section.

Avoid overwhelming the learner with 20 cards immediately.

### B. Mental model

Start the subject with a clear high-level explanation.

For technical material, a simple diagram is often helpful.

For example:

Client → Request → Server → Response → Client

Explain what happens at each step.

A learner should understand the broad picture before learning every implementation detail.

Do not present a complex architectural diagram without explaining how to read it.

### C. Lessons

Each lesson should generally include:

1. An intuitive explanation.
2. A concrete example.
3. The precise technical mechanics.
4. An explanation of why those mechanics matter.
5. Common mistakes.
6. A short understanding check.

Not every section needs identical formatting.

Avoid turning the entire guide into a repetitive template.

### D. Practice

Provide opportunities to apply the lesson.

Useful practice types include:
- Predicting an outcome.
- Editing a request.
- Choosing the correct parameter.
- Diagnosing an error.
- Completing a code snippet.
- Explaining why something happens.
- Ordering steps in a process.
- Comparing two implementations.
- Reconstructing a solution independently.

Practice should help learners recognize what they understand and what they still need to work on.

### E. Reference

Provide useful quick-reference material where appropriate.

Examples:
- HTTP status code reference.
- Request-method comparison.
- Syntax cheat sheet.
- Troubleshooting checklist.
- Common interview questions.
- Searchable terminology.
- Common implementation patterns.

Reference material should be easy to revisit without navigating the entire course.

### F. Capstone

For sufficiently substantial subjects, finish with an exercise combining several concepts.

The capstone should resemble the work the learner is preparing to perform.

Do not introduce completely new requirements without teaching the necessary foundations.

Provide clear objectives, feedback, optional hints, and a complete explanation afterward.

## 7. Navigation

Navigation is essential for long study guides.

Someone should never feel lost inside a large HTML file.

### Desktop layout

Consider:
- A compact left sidebar.
- A central reading column.
- Optional contextual reference or practice content.

A sidebar around 240–272px is a reasonable starting point.

Keep the main reading area comfortable.

Do not create a huge, empty gutter that unnecessarily compresses the content.

### Sidebar

The sidebar should:
- Show meaningful lesson names.
- Indicate the current lesson.
- Make completed lessons recognizable.
- Support returning to previous lessons.
- Group related subjects.
- Remain visually quiet.

Use labels such as:

"Headers and bodies"

Not:

"Module 04"

Numbers can accompany descriptive titles.

### Mobile

Do not simply squeeze the desktop layout into a narrow screen.

Use a labeled navigation drawer or disclosure.

Keep essential actions reachable.

Prioritize reading and practice.

Avoid horizontal page overflow.

Ensure code blocks scroll independently.

### In-page navigation

Provide clear previous and next actions.

If the learner returns to the guide, offer a reasonable way to continue.

Do not unexpectedly change the current lesson.

Do not hijack scrolling.

Do not trigger automatic navigation after someone answers a question.

## 8. Interactivity must teach something

Do not add interactive controls merely to make the guide look sophisticated.

Every interaction must have a learning purpose.

Ask:

"What will the learner understand better after interacting with this?"

If the answer is unclear, reconsider the interaction.

### Good interactive patterns

#### Step-through explanations

Useful for processes with multiple stages.

Example:
1. Construct a request.
2. Resolve the hostname.
3. Establish a secure connection.
4. Send the request.
5. Receive a response.
6. Parse the response.

Let the learner move forward and backward.

Explain the current step.

Do not autoplay complicated processes.

#### Adjustable simulations

Allow the learner to change inputs and see outcomes.

For example:

An HTTP request builder with:
- Method.
- URL.
- Query parameters.
- Headers.
- JSON body.
- Request preview.
- Response preview.

Changing the body should update the outgoing request representation.

Changing the authentication header should affect a simulated authorization outcome.

Every response should follow consistent rules.

Clearly identify simulations as simulations.

#### Debugging labs

Present a realistic broken implementation.

Show:
- The code.
- The observed symptom.
- Relevant logs or response information.
- A way to inspect or change the request.
- A way to test a proposed fix.

Provide informative feedback.

Do not reduce every debugging exercise to multiple-choice trivia.

#### Predict-before-reveal

Show an example and ask the learner to predict what happens.

Allow the learner to commit to an answer.

Then reveal the outcome and explain it.

This is usually more effective than immediately exposing the result.

#### Interactive code comparisons

Show two related implementations.

Allow the learner to compare behavior.

Explain exactly what differs.

For example:

```python
requests.post(url, json=payload)
```

versus:

```python
requests.post(url, data=payload)
```

Teach the difference between JSON serialization and form encoding.

Do not merely say that one is correct and the other is wrong.

#### Progressive hints

When someone gets stuck, offer help in stages.

Hint 1: Point toward the relevant concept.

Hint 2: Identify the relevant part of the problem.

Hint 3: Suggest a specific approach.

Solution: Explain the complete answer.

Do not reveal the entire solution on the first hint.

### Interaction anti-patterns

Avoid:
- Buttons that do nothing.
- Fake terminals that cannot accept input.
- Decorative code editors.
- Quizzes without explanations.
- Animations that run without learner control.
- Flashcards that automatically expose their answers.
- Interactive diagrams with no meaningful state.
- Fake progress indicators.
- Fake AI chat experiences.
- Unnecessary drag-and-drop exercises.
- Game mechanics unrelated to learning.

The interactive experience should be genuinely useful, not merely visually convincing.

## 9. Gentle feedback

Feedback is one of the most important parts of the experience.

A learner should feel comfortable being wrong.

Avoid condescending language.

Bad:
"Oops! That's totally wrong!"

Bad:
"You're a genius! Amazing job!"

Better:
"Not quite. The request body is where the JSON payload is sent. Query parameters are part of the URL."

Better:
"Correct. Using `json=payload` serializes the dictionary and sets the JSON content type."

Good feedback:
- States what happened.
- Explains why.
- Identifies the relevant concept.
- Suggests what to try next.
- Allows another attempt.

Never shame learners for mistakes.

Never celebrate trivial actions with exaggerated enthusiasm.

A gentle tone should feel natural rather than performative.

## 10. Progressive disclosure

Large subjects require careful information management.

Do not show everything at once.

But do not hide essential teaching content.

Good uses of progressive disclosure:
- Optional technical deep dives.
- Additional examples.
- Detailed protocol traces.
- Extended explanations.
- Interview tips.
- Solutions.
- Advanced edge cases.

Poor uses:
- Hiding the central explanation.
- Requiring several clicks to find definitions.
- Collapsing every paragraph.
- Making users repeatedly open and close sections to understand a concept.

Default to showing the material needed to understand the current lesson.

Let advanced information be available without making it mandatory.

## 11. Readability and information density

Use a calm exterior with detailed material inside.

A comprehensive guide may contain thousands of words.

That is acceptable.

The problem is not length.

The problem is making length feel exhausting.

Improve readability through:
- Logical section boundaries.
- Short introductory explanations.
- Clear subheadings.
- Worked examples.
- Relevant diagrams.
- Restrained visual emphasis.
- Carefully placed exercises.
- Consistent navigation.
- Useful whitespace.

Avoid excessively fragmented writing.

Not every sentence needs its own card.

Not every paragraph needs a heading.

Related ideas should remain together.

Use tables when comparison is genuinely easier in table form.

Use diagrams when spatial or procedural relationships are easier to understand visually.

Use prose when prose is the clearest medium.

## 12. Code presentation

Technical education requires excellent code presentation.

### Code blocks

Use:
- Readable monospace typography.
- Clear indentation.
- Appropriate syntax highlighting.
- Horizontal scrolling.
- Copy controls when useful.
- Descriptive labels.
- A distinction between input and output.

Do not place enormous code blocks without context.

Explain the purpose of important lines.

### Code explanations

For example:

```python
payload = {
    "paths": [coordinates],
    "markers": []
}

response = requests.post(
    url,
    json=payload,
    timeout=10
)
```

Explain:
- `payload` is a Python dictionary.
- `paths` and `markers` are fields expected by the API.
- `json=payload` serializes the dictionary into JSON.
- Requests sets the appropriate content type.
- `timeout=10` limits how long the client waits under Requests' timeout semantics.
- The response must still be checked for errors.

Do not assume the learner knows why each API-specific field exists.

### Code correctness

Code must either:
- Actually execute in the intended environment.
- Be clearly presented as illustrative code.
- Or be labeled as a deterministic simulation.

Never imply that simulated code performed a real network operation.

When code cannot execute in a browser, explain the limitation.

Use realistic examples and valid syntax.

## 13. Diagrams

Diagrams should reduce confusion.

Preferred characteristics:
- Simple.
- Purposeful.
- Consistent.
- Clearly labeled.
- Visually restrained.
- Accessible.
- Responsive.

Useful diagrams might show:
- Client-server communication.
- Request lifecycles.
- Authentication flows.
- Data transformations.
- State transitions.
- Retry sequences.
- System architecture.
- Dependency relationships.

Prefer native HTML, CSS, and SVG when practical.

Avoid decorative illustration when a simple diagram communicates more clearly.

A complicated diagram should be explainable in steps.

If a diagram is interactive, its current state should be obvious.

Provide an accessible text description.

## 14. State and progress

For longer guides, track useful progress.

Potential state:
- Completed lessons.
- Completed exercises.
- Current lesson.
- Learner-selected preferences.
- Last visited section.

Use localStorage when available.

Wrap reads and writes in try/catch.

Provide a memory-only fallback if storage is unavailable.

Never claim persistent progress when it is not actually saved.

### Completion

Completion should reflect meaningful activity.

Do not equate scrolling to the bottom with mastery.

A learner may explicitly mark a lesson complete.

An exercise may be marked complete after a real submission.

Distinguish between:
- Viewed.
- Practiced.
- Completed.
- Confident.

Do not present a quiz score as proof of mastery.

### Reset

Provide a clear reset option when meaningful state exists.

Resetting progress should require confirmation.

Do not discard learner input unexpectedly.

## 15. Accessibility

Accessibility is part of kindness.

It is not an optional polish step.

Use:
- Semantic HTML.
- Proper heading order.
- Native buttons.
- Labeled inputs.
- Keyboard-accessible controls.
- Visible focus indicators.
- Appropriate contrast.
- Accessible descriptions.
- ARIA live regions for dynamic feedback when appropriate.

Examples:

```html
<main>
  <section aria-labelledby="lesson-title">
    <h1 id="lesson-title">Understanding HTTP requests</h1>
  </section>
</main>
```

```html
<label for="request-method">Request method</label>

<select id="request-method">
  <option value="GET">GET</option>
  <option value="POST">POST</option>
</select>
```

```html
<div role="status" aria-live="polite">
  Request updated.
</div>
```

Avoid unnecessary ARIA when native HTML already provides correct behavior.

Test keyboard navigation.

Ensure essential controls work without hover.

Aim for comfortable touch targets around 44px where practical.

Respect reduced-motion preferences.

The interface should remain usable at narrow widths and increased browser zoom.

## 16. Motion and interaction polish

Motion should communicate changes in state.

It should not exist to impress the learner.

Good motion:
- A subtle button state transition.
- A sidebar expanding.
- A panel entering or leaving.
- A progress state changing.
- A small visual transition between simulation steps.

Avoid:
- Excessive entrance animations.
- Floating elements.
- Pulsating buttons.
- Parallax.
- Scroll hijacking.
- Animated gradients.
- Constantly moving diagrams.

Use restrained transitions, generally around 120–220ms when appropriate.

Honor `prefers-reduced-motion`.

Never make the learner wait unnecessarily for animations.

## 17. Technical implementation

When the user requests an HTML file, create an actual HTML artifact.

Do not substitute a text explanation.

### Standalone HTML

Prefer a self-contained file when requested.

A single file may include:
- Semantic HTML.
- Internal CSS.
- Vanilla JavaScript.
- Inline SVG.
- Embedded lesson content.
- Local state handling.

Avoid unnecessary build systems.

Avoid remote dependencies unless allowed.

Do not require an internet connection for an explicitly offline guide.

The file should work when opened directly through `file://`.

### Frameworks

Do not assume React is necessary.

Use plain HTML, CSS, and JavaScript when they are sufficient.

Use a framework only when the application's complexity genuinely benefits from it or the user requests one.

Do not sacrifice portability merely to use a familiar development stack.

### Security

Never encourage the learner to paste production credentials into an untrusted page.

Use placeholder API keys.

Do not embed secrets.

Escape user-controlled values.

Prefer `textContent` over unsafe `innerHTML` insertion.

Avoid external trackers.

Explain network and browser security restrictions where relevant.

## 18. Example application: HTTPS and API integration interview guide

This section demonstrates the expected depth for a substantial technical study guide.

User request:

"Teach me HTTPS and API requests end to end for an interview. I need a study guide for the integration side of things. Put it in HTML, interactive, everything I need to know."

Do not produce a superficial article containing definitions.

Build a structured educational application that genuinely prepares the learner to understand, write, and debug API integrations.

### Desired outcome

By the end, the learner should be able to:
- Explain the lifecycle of an HTTP request.
- Understand what HTTPS adds.
- Read API documentation.
- Construct request URLs.
- Choose appropriate HTTP methods.
- Work with headers.
- Serialize JSON correctly.
- Send requests with Python or JavaScript.
- Interpret responses.
- Handle authentication.
- Recognize common errors.
- Debug unfamiliar integrations.
- Implement basic retries safely.
- Handle pagination and rate limiting.
- Complete a practical integration exercise.

### Suggested curriculum

#### Lesson 1: The complete request lifecycle

Explain:

Client → DNS → Connection → TLS → HTTP request → Server → HTTP response

Clarify that the transport depends on the HTTP version: HTTP/1.1 and HTTP/2 commonly use TCP with TLS for HTTPS, while HTTP/3 uses QUIC.

Teach:
- What HTTP is.
- What HTTPS is.
- What TLS protects.
- What DNS does.
- Why a client needs a connection.
- How a server receives and processes requests.
- How a response returns.

Interaction:
A step-through request lifecycle.

Allow the learner to inspect each stage.

#### Lesson 2: Anatomy of a URL

Teach:
- Scheme.
- Hostname.
- Port.
- Path.
- Query parameters.
- Fragment.

Interaction:
Let the learner construct a URL from editable fields.

Show the resulting URL in real time.

Explain which components are sent to the server and how.

#### Lesson 3: Anatomy of an HTTP request

Teach:
- Methods.
- Headers.
- Request body.
- Query parameters.
- Content types.
- Accept headers.

Compare:
- GET.
- POST.
- PUT.
- PATCH.
- DELETE.

Explain method semantics without suggesting the method name alone guarantees server behavior.

Interaction:
Show a request inspector.

Let the learner adjust method, headers, URL, and body.

#### Lesson 4: JSON serialization

Teach:
- Python dictionaries.
- JSON objects.
- Serialization.
- Deserialization.
- Content-Type.
- Encoding.

Compare:

```python
requests.post(url, json=payload)
```

with:

```python
requests.post(url, data=payload)
```

Explain why these are not interchangeable.

Interaction:
Allow the learner to switch between serialization approaches.

Show the corresponding simulated request body and content type.

#### Lesson 5: Reading API documentation

Teach how to identify:
- Base URL.
- Endpoint.
- Request method.
- Authentication.
- Required fields.
- Optional fields.
- Request schema.
- Response schema.
- Error codes.
- Rate limits.
- Pagination.

Interaction:
Present abbreviated fictional API documentation.

Ask the learner to construct a valid request.

#### Lesson 6: Authentication and authorization

Teach:
- API keys.
- Bearer tokens.
- OAuth at a conceptual level.
- Authentication versus authorization.
- Common authentication headers.
- Credential handling.

Interaction:
Show how simulated authentication states affect request outcomes.

Never request real credentials.

#### Lesson 7: Responses and status codes

Teach:
- Response status.
- Headers.
- Response body.
- JSON parsing.
- Successful and unsuccessful responses.

Cover:
- 200.
- 201.
- 204.
- 400.
- 401.
- 403.
- 404.
- 409.
- 422.
- 429.
- 500.
- 502.
- 503.

Interaction:
Show a response and ask the learner to diagnose it.

Explain why the status occurred and what to inspect next.

#### Lesson 8: Debugging API integrations

Teach common failures:
- Incorrect endpoint.
- Missing required field.
- Wrong content type.
- Invalid JSON.
- Missing token.
- Expired token.
- Incorrect HTTP method.
- Timeout.
- Rate limiting.
- Unexpected response schema.

Interaction:
Create a debugging lab.

Show broken code and an observed symptom.

Allow the learner to inspect and correct the problem.

#### Lesson 9: Reliability

Teach:
- Timeouts.
- Retries.
- Exponential backoff.
- Jitter.
- Idempotency.
- Rate limiting.
- Pagination.
- Error handling.
- Logging without leaking secrets.

Interaction:
A simulated request timeline.

Allow learners to change retry policy and see how it affects outcomes.

#### Lesson 10: Integration interview simulation

Create a fictional API integration task.

Give the learner:
- A README.
- API documentation.
- A starter implementation.
- Requirements.
- Example requests.
- Error cases.
- Tests or deterministic validation.
- Optional hints.

Example:

Build a request body containing:

```json
{
  "paths": [
    [
      [-118.44, 34.07],
      [-118.45, 34.08]
    ]
  ],
  "markers": []
}
```

Require the learner to:
- Understand the schema.
- Construct the payload.
- Select the correct request method.
- Send JSON.
- Handle the response.
- Diagnose a failure.

The capstone should connect the entire curriculum.

### Interface expectations

This example should include:
- A lesson outline.
- A readable central lesson area.
- Interactive request builder.
- Request/response inspector.
- Debugging lab.
- Understanding checks.
- Progressive hints.
- A compact reference section.
- A capstone.
- Meaningful progress tracking.

However, do not add features that do not improve the learning experience.

A focused, well-executed tool is preferable to a sprawling interface full of shallow widgets.

## 19. Interaction patterns for technical subjects

Choose the interaction based on the knowledge being taught.

| Learning goal | Preferred interaction |
| --- | --- |
| Understand a process | Step-through diagram |
| Learn request structure | Interactive request builder |
| Understand data transformation | Before/after comparison |
| Learn syntax | Editable code example |
| Diagnose failures | Debugging lab |
| Compare alternatives | Side-by-side comparison |
| Remember distinctions | Retrieval practice |
| Apply several concepts | Capstone exercise |
| Review material | Compact reference |
| Explore optional complexity | Progressive disclosure |

Never assume every lesson needs an interaction.

Sometimes a clear explanation and one well-chosen example are enough.

## 20. Content quality

The educational content matters more than the CSS.

Do not generate polished interfaces with shallow explanations.

For each substantial concept, ask:
- Is this technically accurate?
- Is the explanation understandable?
- Does the example actually illustrate the concept?
- Have important prerequisites been covered?
- Could the learner explain this in their own words?
- Could the learner use this knowledge independently?
- Have common misconceptions been addressed?

If the answer is no, revise the lesson.

### Verify factual claims

For technical material:
- Prefer official documentation.
- Verify details when tools are available.
- Distinguish standards from library-specific behavior.
- Avoid outdated examples.
- Do not invent API guarantees.
- Do not invent interview expectations.
- Clearly label assumptions.

### Teach causally

Prefer explaining why an outcome occurs.

Weak:
"401 means unauthorized."

Better:
"A 401 response usually means the request lacks valid authentication credentials. First inspect whether the expected authentication header was sent, whether the token is valid, and whether the API expects a different authentication mechanism."

Understanding causes is more useful than memorizing labels.

## 21. Writing style

Write like a thoughtful engineer explaining a concept to another intelligent person.

Use:
- Direct explanations.
- Natural language.
- Concrete examples.
- Clear transitions.
- Precise terminology.
- Calm encouragement.
- Helpful questions.

Avoid:
- Corporate marketing language.
- Excessive enthusiasm.
- Repetitive motivational copy.
- Forced analogies.
- Unnecessary jargon.
- Long decorative introductions.
- Artificially inspirational language.
- Generic AI-sounding phrases.
- Patronizing reassurance.

Do not use emoji as the primary method of communicating tone.

Friendliness should come from usefulness, anticipation, and clarity.

### Example

Bad:

"Welcome to your ULTIMATE API MASTERCLASS! Get ready to unlock the power of HTTP and become an API wizard!"

Better:

"Let's understand what actually happens when your code makes an API request. We'll build a request, inspect what gets sent, and learn how to debug it when something goes wrong."

The second version is calmer, clearer, and more respectful.

## 22. Empty states and errors

Every state should help the learner understand what to do next.

### Empty states

If no progress exists:
"Start with the first lesson. Your completed lessons will appear here."

If a search has no matches:
"No matching topics. Try a different term."

If an exercise has not been attempted:
"Make a prediction, then check your answer."

### Errors

If user input is invalid:
"That isn't valid JSON yet. Check that the keys use double quotes and that there are no trailing commas."

If local storage is unavailable:
"Progress will work during this session, but may not be saved when you close the page."

Avoid vague errors such as:
"Something went wrong."

Explain what happened when possible.

Provide a recovery path.

## 23. Review the design before delivery

Perform a visual and functional review.

### Visual review

Check:
- Does it feel calm?
- Is the hierarchy obvious?
- Is typography comfortable?
- Are components visually consistent?
- Is there excessive decoration?
- Are colors purposeful?
- Does whitespace help organization?
- Are there unnecessary borders?
- Is the content column readable?
- Is the mobile layout genuinely usable?

### Learning review

Check:
- Can someone understand where to begin?
- Are prerequisites introduced first?
- Does each lesson serve a purpose?
- Do examples build on previous explanations?
- Are interactions meaningful?
- Is feedback informative?
- Can someone revisit concepts easily?
- Does the guide actually prepare them for the stated goal?

### Functional review

Test:
- Navigation.
- Previous/next controls.
- Interactive inputs.
- Quizzes.
- Hint systems.
- Reset controls.
- Progress tracking.
- Local storage fallback.
- Copy actions.
- Keyboard navigation.
- Responsive behavior.
- Reduced-motion behavior.
- Error states.

If browser inspection is available, inspect the rendered page.

Do not rely only on the fact that the HTML was generated successfully.

### Accessibility review

Check:
- Heading structure.
- Keyboard controls.
- Focus visibility.
- Labels.
- Contrast.
- Screen-reader announcements.
- Zoom behavior.
- Touch targets.
- Reduced-motion preferences.

Fix obvious problems before delivering.

## 24. Acceptance rubric

Rate the result against these ten criteria.

Each criterion must pass.

1. **Immediate orientation:** The learner understands the purpose and where to begin within ten seconds.
2. **Educational depth:** The material genuinely teaches the requested subject rather than listing concepts.
3. **Clear navigation:** Long guides remain easy to navigate, including on mobile.
4. **Meaningful interaction:** Interactive elements teach, validate, demonstrate, or reinforce knowledge.
5. **Technical correctness:** Examples and explanations are accurate and internally consistent.
6. **Gentle feedback:** Mistakes produce useful explanations and allow recovery.
7. **Accessible design:** Reading, keyboard usage, contrast, focus, and reduced motion are handled thoughtfully.
8. **Honest state:** Progress and simulations accurately represent what has happened.
9. **Visual quality:** The experience feels refined, coherent, warm, and intentionally designed.
10. **Functional completeness:** The HTML works in its intended environment and has no knowingly broken controls.

Revise any failing criterion.

Do not claim that functionality was tested unless it actually was.

## 25. Final output requirements

When the user asks for an HTML guide:

1. Produce the actual HTML.
2. Make it complete and usable.
3. Include the educational content, not placeholder lessons.
4. Implement the promised interactions.
5. Keep it standalone if requested.
6. Ensure examples and simulations are labeled accurately.
7. Verify functionality when tooling permits.
8. Provide the resulting file.
9. Briefly explain what is included.

Do not stop after creating a design specification.

Do not deliver a mockup instead of a working learning tool.

Do not generate a generic dashboard and fill it with study text.

The result should be an actual learning experience.

## 26. Final principle

The most important design principle is this:

**Make difficult things feel approachable without making them simplistic.**

A good study guide should make the learner feel that the subject is understandable, that progress is possible, and that the interface is helping rather than demanding attention.

The learner should not have to work hard to use the learning tool.

They should be able to spend that effort on learning.

Build something calm, precise, complete, and genuinely pleasant to return to.
