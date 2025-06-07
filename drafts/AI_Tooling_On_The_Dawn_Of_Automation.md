# AI Tooling on the Dawn of Automation

Obsessed with the current wave of tooling I have tried everything, written PRs to Aider(link to my aider), got frustrated wrote my own tooling, gotten frustrated and mostly gone back to using the what works.

Somewhere along the journey I've become incredibly opinionated about AI tooling and have some thoughts to share.



Self-Service Models
OpenRouter Support is the key choice for me here, I want to bring my own key and access the models at the market API rates. Cursor wants to upcharge me do all sorts of special logic. That's cool they want to make money, but I don't want to think too hard. My work might have the budget to let me spam Claude 4 Opus, but at home those free preview models that train on my data are wa too fun to pass up.


This comes along with the beneifts of usually being self-service, and also the benefit of full transparency, no hideen system prompts, no rediction to slow queue. Some of this is burden, but I think there will be a 10-20% who wants to really knows what they're tools ar doing
and as an added beneift, if you are working with LLMs at your day job it's an easy way to get a sense for the different models. Part of your job is knowing what prompts work best, what style differnet models output, what domains they accelerate in. And using
models on coding as something you already know your way around gives you a strong baseline for how the models are performing. I spent a day with
inception/mercury-coder-small-beta as a diffusion LLM to get a sense of if all the google diffusion hype is just cherrypicking. NOTE: It's not, LLM's are about to get dramatically faster. Adjust you priors.

Building my own tools.
AI-OS is my second crack at wrting an agent. The first one was a nasty mess I'd rather you not find on github two years ago that failed with the slow as hell
and dumb models we. This attempt is much better designed, but more importantly actually works. This time I decided, acutally no agents, tool use
is chaotic and I end up checking in and running and writing tests to keep the damn things on the rails anyway.

AI-OS works "like" an agent. You just talk to a terminal and it runs loops. But instead it's actually designed to evaluate "AI Macros" AI-OS is a small
python run time that does a particualrly small number of things:
 * Manages LLM code applications via patches
 * Maintains history and context for LLM calls
 * Connects to a repl UI for user interaction

And AI Macros are just python programs that use this runtime.

Thats it. It's a small set of functions you can call in a python program to write you own agent. The fiddly bits are down for you and 
the rest gets out of your way.

Here is an example of me using it to write a new shader:

[TODO: Add a screen recording]

Some thigs that I haven't seen supported else where you can do with
* Custom test time compute strategies(Fan out and try 10 times in parallel)
* LLM's as judges for test time development(Shader renders and UI's can't pass tests! now they can with VLLMs)
* Deterministic test checks and file freezeing(No longer rely on your LLM to promise the test passes, or having it re-write tests, keep your tests clean, deterministic and accurate)
* Anything else!(You have all of python at your disposal, do what ever you want)


What do I use for work "Cursor with Claude 4.0 Opus"(Sonnet sometimes) (NOTEL This has change but for work I generally pikc the best model fro a while that 
was o1-pro via chatGPT UI and I did a lot of copy pasting

At home I use "Roo Code" Hackable and free (Check out the extensible memories systems people are dremaing up) Supports open router, and generally an
all around great piece of work with a well tested set of practical choices.
