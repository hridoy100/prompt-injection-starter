# Getting Started With AI Security: Prompt Injection 101

Prompt injection is the fastest way to see how AI systems can be tricked. In short, an attacker uses crafted input to override instructions, leak data, or change how a model behaves. This post is a quick, practical starting point with a few high-signal resources to learn the basics and experiment safely.

## Why Prompt Injection Matters

Large language models often follow the most recent or most persuasive instructions they see. That makes any system that mixes user input with privileged instructions (like system prompts, tool calls, or hidden policies) a target. Understanding prompt injection helps you design safer apps, test your own systems, and speak clearly about risk.

## A 30-Minute Starter Path

1. Read a concrete example of how attackers smuggle instructions into prompts.
2. Explore a couple of public prompt injection challenges to build intuition.
3. Browse a curated library of attacks to learn common patterns.
4. Follow a couple of long-form sources for deeper dives.

## High-Signal Resources

### Concepts and Techniques

- [ASCII Smuggler](https://embracethered.com/blog/ascii-smuggler.html) - Clear explanation of how hidden instructions can bypass filters.
- [Prompt Injection Tag on Medium](https://medium.com/tag/prompt-injection-attack) - A rolling set of articles and case studies.

#### ASCII Smuggler: How to Use (Safely)

ASCII smuggling hides instructions in characters that look like normal text but are interpreted differently by machines. Use it as a defensive exercise to learn what your system should detect and normalize.

1. Read the blog post end-to-end and note the example payloads.
2. Copy an example into a plain text editor that can show invisibles (see quick options below).
3. Compare the visible text vs. the underlying characters to see what a filter might miss.
4. In your own sandbox app, log both the raw input and a normalized version (e.g., strip or replace suspicious characters).
5. Add a simple detector that flags non-printing or unexpected Unicode ranges and review how often it triggers.

Quick options to reveal hidden characters:

- VS Code: enable "View: Render Whitespace" and "View: Toggle Render Control Characters".
- Sublime Text: "View" -> "Show White Space" (and install a control character plugin if needed).
- macOS Terminal: `cat -v file.txt` to show control chars as caret codes.

Tiny Python helper to visualize suspicious characters:

```python
def show_non_ascii(s):
    for i, ch in enumerate(s):
        if ord(ch) < 32 or ord(ch) > 126:
            print(i, hex(ord(ch)), repr(ch))
```

### Practice and Challenges

- [Prompt Airlines](https://promptairlines.com/) - Interactive prompt injection challenges with real feedback.
- [L1B3RT4S](https://github.com/elder-plinius/L1B3RT4S) - Community prompts for testing model behavior under adversarial input.
- [Damn Vulnerable LLM Agent](https://github.com/ReversecLabs/damn-vulnerable-llm-agent) - A ReAct-based agent challenge for practicing jailbreaks and prompt injection.

### Libraries and Collections

- [MyLLMBank](https://myllmbank.com/) - A large collection of prompt injection examples and jailbreaks.

### Longer Reads and Media

- [Executive Offense - LLM Hacking PT 2](https://executiveoffense.beehiiv.com/p/executive-offense-llm-hacking-pt-2) - Practical, offensive view of LLM testing.
- [Adversarial ML YouTube Playlist](https://youtube.com/playlist?list=PLALM3TzRCwCsNM1wC1-LY9z8nlhAsd2v8&si=pIdOe_AyzuQly6ox) - Talks and lectures for broader context.
- [Prompt Injection Talk](https://www.youtube.com/watch?v=43qfHaKh0Xk) - A focused walkthrough of prompt injection concepts.
- [Certified AI/ML Pentester Exam Journey](https://medium.com/@gavilanesadolfo/certified-ai-ml-pentester-certification-exam-journey-64e151d39dcd) - A realistic look at learning pathways.

## Quick Tips for Safe Learning

- Test only in sandboxes or on systems you own.
- Keep logs of prompts and outputs; they become your best debugging tool.
- Start with simple goals: exfiltrate a hidden string, override a policy, or force tool misuse.
