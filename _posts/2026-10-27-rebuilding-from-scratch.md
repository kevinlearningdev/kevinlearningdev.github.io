---
layout: post
title: "My AI-Built App Worked, and That Was a Problem for Learning"
---

**Read time:** ~5 min &nbsp;|&nbsp; **Word count:** ~1,100 &nbsp;|&nbsp; **Topic:** Learning with AI &nbsp;|&nbsp; **Skills/tech:** AI-assisted coding (Claude), LLM apps, Python

## TLDR
- **Goal:** Get better as a software engineer by building an AI app, not just end up with an app that works.
- **Summary:** I let AI build my Japanese flashcard app in about an hour. It worked, but I couldn't explain how, and every bug fix was whack-a-mole. Since my real goal is to grow as an engineer, I'm rebuilding it from scratch in small chunks: about 200x slower, and far more satisfying.
- **Takeaway:** Be clear about your goal. If it's learning, take the time to understand what the AI builds.

---

The local models in my Japanese flashcard app couldn't read the on-screen text, especially colored captions with poor contrast.
The AI suggested a fix, I said go for it, and it didn't work.
It tried something else.
Didn't work.
Another thing.
Didn't work.
Then, wait, this one worked!
I had no idea why.

I'm trying to get better as a software engineer by building an AI app: one that uses generative models, to do real work.
What I've come to realize is that if I don't take the time to understand what I'm building, it's just a lot of whack-a-mole.

## A tool looking for a problem

It started with Tina Huang's video [Open Source AI In 17 Minutes](https://www.youtube.com/watch?v=1uCE0uoKXL8), about using open-source AI to build personal workflows that cut friction and manual busywork.
What hooked me was the cost.
Open-source models are free, Modal gives you $30 of free compute credit a month for the heavy ones, and lighter models run fine on my M2 Pro MacBook.
Zero cost to try this and learn it.

Then a few weeks went by, and I still didn't know what to build.
Nothing in my routine rose to the level of needing an LLM or an AI agent, and I don't run a business (yet).

## A problem looking for a tool

Meanwhile, I'd taken a flash trip to Japan: two days, one night, basically a long layover.
I grew up on anime and manga, and I've followed One Piece for something like 30 years (29? 31? it's been a long time), so wanting to understand Japanese without a translation wasn't new.
The trip just made it solid.

Learning Japanese takes real mental energy, so after hiragana I went for the lowest-effort option I could find: doom scrolling.
Short-form videos on Instagram and TikTok, in pure Japanese, ideally with subtitles burned in.
The standard advice is that immersion beats random drills, and it even replaced my regular doom scrolling.
Slightly productive doom scrolling!

The frustration was that I had no idea what was going on.
I wanted something built around what I was actually watching: screenshot a sentence, turn it into an Anki card, and really study it.
While I was chatting with Claude about how that could work, it pointed out that AI models could do most of it, and it clicked.
The app could be built with AI and would run on AI models: a problem I could finally point my itch at.

Of course, someone had already built it.
Migaku does something very close, and open-source tools cover most of it too.
It didn't matter.
This was a learning exercise.

## An app I couldn't explain

At work I use AI to write a lot of code, but carefully: I have to own that code, stand behind it, and maintain it.
For the prototype, I defined the key requirements and the rough shape of a card and the pipeline, and let the AI rip.
In about an hour, plus some churning through bugs, I had a working prototype, and I started using it.

Then I looked at the code, and my eyes glazed over.
A few thousand lines: a frontend, an API, the model calls, much of it messy the way LLM-generated code often is, and a lot of it stuff I'd never seen.
I knew how the app worked at the level of the requirements and design I'd written.
How it actually worked, like that text-recognition fix, I couldn't tell you.
And building it hadn't made me a better engineer.

Why not just read the code until I understood it?
For me, that much code is drinking from a fire hose: I glaze over, ask the AI to explain a few things, and move on.
There were so many questions I didn't know where to begin.
Small chunks work better.
A narrow scope gives me an anchor: I can think one piece through, see how it fits the bigger picture, and see exactly where I'm stuck.

So I'm starting over.

## Same design, different builder

The design and the stack carried over completely; this is a restart for the sake of learning.
AI still writes every line of the code.
The difference is that I take the time to understand it, and I don't try to understand everything equally.
I go deep on the AI engineering: calling models, chaining them together, and keeping the code modular when different models do different chores.
The API and frontend get a lighter touch.

The bigger change is being active instead of passive.
Accepting or rejecting a suggestion is a decision I actually make, instead of riding along with whatever the AI generated.
When Claude proposed the interface for a "model step," one stage of the pipeline that calls a model, I went through its design decisions one at a time.
I asked what the `In` and `Out` in `ModelStep[In, Out]` meant, and learned Python 3.12's syntax for generics along the way.
I asked whether the model name and effort setting belonged on the input side, and was convinced by the answer: the result is a receipt of what actually ran.
I disagreed with one proposal, came around after thinking it through, and pushed for clearer naming on another.
None of it was dramatic, but every piece of that interface is now something I chose.

Is it slow?
Very.
The prototype took about an hour; I've spent at least ten hours on the rebuild and I'm maybe 5% in.
That's somewhere around 200 times slower, so I'm choosing not to do the math.
If I were testing a business idea, a fast AI-built prototype would be exactly right.
But I'm here to grow as an engineer, and honestly, it's satisfying.
I'm not doing this because engineers are supposed to learn on their own time; I just enjoy building a clean mental map of how the pieces fit and how they should behave.

## Know what you're optimizing for

If there's one takeaway, it's to be clear about your goal.
If it's to learn with AI, spend the time to understand what it builds, at the level you actually care about.
If it's to ship a product and make money, that's a very different game.
There's probably a balance somewhere in the middle, but I haven't found it.

Across this rebuild and my other learning, like the Software Engineer Mindset course I'm taking, I keep finding the same thing: struggling with a problem, guessing at what's going on, and checking whether I was right is what makes a concept actually stick.
That loop deserves its own post.

