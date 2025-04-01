## Rough Notes

## First Steps
Buy good models!
ChatGPT or Claude. Get a plus account—at least $20-40 (These are about equivalent).
But also, o1-pro is worth it—YOLO coding is real.

It's worth $2k a year. I swear.

## Base Models vs. RL

### Base models
These models are so fun. They happen to follow your instructions because they've seen lots of instructions.

RL models follow your instructions because they're compelled by an unyielding reward force to achieve your goal.
The force is effective but narrow.
RL models are like a high-dimensional cone focused toward a single (maybe right) solution.

Base models are like a spider web connecting many solutions, all floating in a log-probability soup.

## Chain of Thought

Chain of Thought is everything. You can do anything besides—but thinking is always contextual.

## Reasoning and Thinking

### Reasoning
Reasoning is...
- Self-prompt planning and self-directed multi-step solving.
- Reasoning emerges naturally from high-quality instruction data.
- (“Let's think step by step”)
- Enhanced by RL, DPO, and reward training.

Reasoning models generally perform Chain of Thought implicitly.
Claude 3 + `<think>` ≈ prompts ≈ Claude 3.5

### Thinking
Thinking is extended reasoning.
You can think and think and think.

[ `<think>` repeated 10 times ] x10
Claude 3 + `<think>` + `(Continue...)` ≈ Claude 3.7 Thinking

Understand Multi-Turn and RL.

- RL is inherently unidirectional.
- Reasoning is inherently unidirectional.
- Thinking is inherently unidirectional.

Unidirectional is anti-CoT.

Fundamentally, once you train a pre-trained model long enough, you invoke point collapse on both input and output.

Filtering on correctness sharpens point collapse on input.

Mapping to less varied input progressively trains models on narrower input data, causing them to progressively de-generalize in context.

## Real Project Notes (Game Prototype with 0% Human-Written Code)

I've been experimenting with a project to create a game entirely with AI-generated code (0% human-written). Partly to build the game, partly to benchmark these new long-context models on a larger, more complex project.

Initially, I tried MCP and Claude Desktop for this—0% coding, including tests and browser runs with MCP. It got about 70% there but then went haywire for several hours and couldn't finish.

This weekend, I finally achieved a working prototype using a different approach—mostly ChatGPT-generated code without MCP.

## Key Takeaways:

- **Work in Chunks:** AI can't handle render+network+state all at once.
- **Rollback:** If AI can't quickly fix an error, revert to a stable checkpoint.
- **Always ask ChatGPT for patches.**
- **Manual testing:** Frequent testing is crucial (AI is overly confident that its code works).
- **Log Everything!** Long-context models thrive on giant, noisy logs—output and print everything.

## Slides

- **Slide 1:** Base Models vs. RL [Graphic PENDING: Visualization of "Spider web" vs. "High-dimensional cone"]
- **Slide 2:** Chain of Thought [Graphic PENDING: Flowchart illustrating Chain of Thought]
- **Slide 3:** Reasoning and Thinking Continuum [Graphic PENDING: Gradient scale from Reasoning to Extended Thinking]
- **Slide 4:** Point Collapse Concept [Graphic PENDING: Visualization of points collapsing towards a single direction (cone-shaped), enhanced with lines illustrating function mappings clearly]
- **Slide 5:** Project Workflow (0% Human-Written Code) [Graphic PENDING: Diagram showing iterative workflow with checkpoints and rollback]
- **Slide 6:** Input Degeneralization [Graphic PENDING: Progressive narrowing of input diversity visualized as shrinking funnels or narrowing paths]

