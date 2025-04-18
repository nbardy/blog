## Rough Notes

These are my rough notes used a draft for creating slides in a short presentation I gave, "How to stop writing Code"

## Use small models to stuff the Context Window
Increasing Context Quality and Length increases
You can use tiny models to stuff context.
e.g. o4-mini "suggest 10 different reasons for this bug", "Suggest 3 different directions to explore"
Use a slower model o1, o1-pro, o3-mini-high to reasoning.
"Check all this work of a dummer model"
Is any of it correct? Suggest a final correct answer and reasoning


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

### Reinforcement Learning Trained Models
Generally more useful as they trade off variance for accuracy.
The base model are hard to get instructed accurately.
Largely the same for instruction tuned model(Requires meticulous testing of prompts)

RL, generally friendly(Narow expected behavior and high averge)
"Doesn't need personas like "act like an nvidia engineer"
Implicitly biases towards highest accuracy answers through training.
~"You can almost always prompt a base model to beat it's RL version"~
"Newer Models such as o1,o3,deepseek-r1 out perform test time compute + prompting"
They do this by training with prompting + in context learning during


Downsides:
As you train them you introduce mode collapse
![image](https://github.com/user-attachments/assets/b0ba2565-8697-46f3-a5d9-901956a6db35)


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


## Key Takeaways(Boring AI Summary)

- **Work in Chunks:** AI can't handle render+network+state all at once.
- **Rollback:** If AI can't quickly fix an error, revert to a stable checkpoint.
- **Always ask ChatGPT for patches.**
- **Manual testing:** Frequent testing is crucial (AI is overly confident that its code works).
- **Log Everything!** Long-context models thrive on giant, noisy logs—output and print everything.

