# prompt-injection-starter

# Prompt Injection 101: A Quick Start

Prompt injection is one of the easiest ways to see how AI systems can be manipulated. Attackers can craft input that overrides instructions, leaks data, or steers behavior. This is a short, practical set of resources to learn the basics and experiment safely.

## Why Prompt Injection Matters

LLMs tend to follow the latest or most persuasive instructions. Any system that mixes user input with privileged instructions (system prompts, tools, or hidden policies) becomes a target. Knowing the basics helps you build safer apps, test your own systems, and discuss risk clearly.

## High-Level Resources

### Concepts and Techniques

- [ASCII Smuggler](https://embracethered.com/blog/ascii-smuggler.html) - How hidden instructions can bypass filters.
- [Prompt Injection Tag on Medium](https://medium.com/tag/prompt-injection-attack) - Articles and case studies.

#### ASCII Smuggler: Safe Practice

ASCII smuggling hides instructions in characters that look normal but parse differently. Use it defensively.

1. Read the post and copy a sample payload into a plain-text editor.
2. Show invisible characters and compare raw vs. visible text.
3. In a sandbox app, log raw and normalized input and watch what changes.

### Practice and Challenges

- [Prompt Airlines](https://promptairlines.com/) - Interactive challenges with feedback.
- [L1B3RT4S](https://github.com/elder-plinius/L1B3RT4S) - Community prompts for adversarial testing.
- [Damn Vulnerable LLM Agent](https://github.com/ReversecLabs/damn-vulnerable-llm-agent) - ReAct-based agent challenge.

### Libraries and Collections

- [MyLLMBank](https://myllmbank.com/) - Prompt injection examples and jailbreaks.

### Longer Reads and Media

- [Executive Offense - LLM Hacking PT 2](https://executiveoffense.beehiiv.com/p/executive-offense-llm-hacking-pt-2) - Practical offensive view of LLM testing.
- [Adversarial ML YouTube Playlist](https://youtube.com/playlist?list=PLALM3TzRCwCsNM1wC1-LY9z8nlhAsd2v8&si=pIdOe_AyzuQly6ox) - Talks and lectures for context.
- [Prompt Injection Talk](https://www.youtube.com/watch?v=43qfHaKh0Xk) - A focused walkthrough of prompt injection concepts.
- [Agentic ProbLLMs: Exploiting AI Computer-Use and Coding Agents (39c3)](https://www.youtube.com/watch?v=TWhKGqYQT9g) - Talk by **Johann Rehberger** (embracethered.com).
- [Certified AI/ML Pentester Exam Journey](https://medium.com/@gavilanesadolfo/certified-ai-ml-pentester-certification-exam-journey-64e151d39dcd) - A realistic learning path.

## Quick Tips for Safe Learning

- Test only in sandboxes or on systems you own.
- Log prompts and outputs so you can debug what happened.
- Start small: try a hidden string leak, policy override, or tool misuse.
