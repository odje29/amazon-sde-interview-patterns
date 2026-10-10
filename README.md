# Amazon SDE interview preparation: the round-by-round plan, the patterns Amazon keeps asking, and where a structured course actually fits

The Amazon SDE process is long enough that "preparation" stops meaning *study more* and starts meaning *sequence things correctly*. You get an online assessment with a hidden test harness, a loop where behavioral questions are embedded inside coding rounds, and a Bar Raiser whose job is to look for the LP signal you're weakest on. Miss the sequence and you can solve every problem and still walk away with a rejection email.

Below is a plan built around how the rounds are actually structured, plus where a pattern-based course like AlgoMonster earns its price and where you'll need something else.

## What the Amazon SDE loop actually looks like

Amazon publishes this itself, which removes a lot of the guessing. For SDE II, the official flow is: application → online assessment → interview loop → result within 5 business days.

The OA is roughly 90 minutes. Two technical questions, then about 20 minutes of system design scenarios, then an 8-minute multiple-choice work style survey tied to the Leadership Principles. The loop itself is four 55-minute interviews with members of the software development community.

New grad and SDE I loops look slightly different. Candidates consistently describe the OA as arriving through HackerRank with two coding problems in a 70–90 minute window, followed by a work style assessment of 15–20 minutes and a work simulation of 35–60 minutes built from realistic workplace scenarios and stakeholder messages. The simulation isn't a personality quiz. It's prioritization under ambiguity, and the "correct" answers track the same principles the interviewers score later.

Two details from Amazon's own candidate guidance matter more than they get credit for:

- You will be asked to write syntactically correct code, not pseudocode. The editor has syntax highlighting but no execution.
- Interviewers are told to expect you to ask clarifying questions before you start typing.

Both are stated on the record by Amazon. Both are also the two things candidates skip when they're nervous.

## The three failure modes that repeat

Reading through dozens of candidate write-ups from recent loops, the rejections cluster around three things, and only one of them is coding ability.

**Pattern selection speed.** Amazon's coding questions skew medium. What separates candidates is how fast you identify the right approach. The reported question list is mundane in a telling way: merge intervals, number of islands, LRU cache, lowest common ancestor of a BST, longest substring without repeating characters, topological sort with cycle detection, min stack, K closest points, a rotated binary search variant. None of these are exotic. All of them are recognizable within 30 seconds if you've internalized the pattern, and unapproachable in 10 minutes if you haven't.

**"We" instead of "I" in behavioral answers.** This is the single most repeated rejection reason in Amazon candidate reports. Interviewers probe with "what did *you* specifically decide?" and a story framed around team contributions collapses. Every coding round also carries 10–15 minutes of behavioral questions, so this isn't confined to the designated LP round.

**No depth on follow-ups.** "How would this change if the input were streamed rather than loaded into memory?" "What happens to your time complexity after that optimization?" Amazon interviewers push on scale and tradeoffs, and a candidate who writes correct code but can't discuss why it's correct at 10 billion records gets marked down.

> The Bar Raiser is a trained interviewer from a different team who doesn't need the role filled. They have veto power, they typically appear in one or two rounds, and they tend to probe exactly the principle where your story is thinnest.

## The DSA half: patterns over problem count

Amazon doesn't avoid hard problems, but the distribution is weighted toward medium, and the topic coverage is narrow enough to plan for. Based on candidate reports and the frequency data that circulates around Amazon loops, these are the families that keep appearing:

| Pattern | Where it shows up | Representative problems |
| --- | --- | --- |
| Hash map lookups | OA and every coding round | Two Sum and variants, group anagrams, top K frequent |
| Two pointers / sliding window | OA, coding rounds, Bar Raiser | Longest substring without repeating characters, subarray optimization |
| Intervals | Coding rounds | Merge intervals, meeting rooms |
| BFS/DFS on grids and graphs | OA almost always | Number of islands, shortest path variants, cycle detection |
| Trees | Coding rounds | LCA, level-order and zigzag traversal, maximum path sum |
| Heaps / top-K | OA and coding rounds | K closest points, task scheduling |
| Binary search | OA and coding rounds | Rotated sorted array, search on answer space |
| Dynamic programming | SDE II coding rounds | Subsequence DP, House Robber variants, knapsack-style optimization |

A useful working number: somewhere between 60 and 100 problems solved with intent is enough to cover this surface, provided at least 20 of them are binary search and graph variants. That's not a lot. The reason people grind 400 problems and still freeze is that volume without pattern attribution doesn't transfer — you memorize solutions, not the decision that picks a solution.

This is where AlgoMonster's approach is aimed. It's a text-and-diagram course built by ex-Google engineers and competitive programmers, organized around reusable coding patterns with decision flowcharts for classifying a new problem before you write anything. The flowcharts are the part that maps directly onto what Amazon tests: the interviewer is measuring whether you arrive at the correct approach quickly, not whether you can eventually get there.

If you want to see how the pattern curriculum is structured before spending anything, 👉 [start with AlgoMonster's free tier and the pattern list](https://algo.monster?fpr=li69).

## The behavioral half: 16 principles, 10 stories, and numbers

Amazon's 16 Leadership Principles aren't a separate round. They're the grading rubric that runs underneath every round, including the technical ones.

The practical preparation is:

1. **Build 8–12 distinct stories.** Not 16 — you'll reuse. Map each one to two or three principles.
2. **Frame everything as "I."** What you decided, what you escalated, what you shipped, what you traded away.
3. **Quantify the Result.** "Reduced P99 latency from 340ms to 120ms by rebuilding the caching layer" is a result. "The project was successful" is not, and at L5 it's an automatic downgrade.
4. **Spend most of your airtime on Action.** Situation gets two sentences. The mechanism you chose gets the rest.
5. **Prepare for layered follow-ups on the same story.** What were the numbers, what would you change, what did the other person say.

Established engineers can also expect an AI-usage question in the hiring-manager round — candidate reports from recent loops mention "how do you use AI in day-to-day work" appearing alongside standard LP questions. Worth having a real answer ready.

AlgoMonster includes some behavioral content, but it isn't built for this. Be honest about that when you budget. The LP work is writing, not studying — you can do it in a notes file with no subscription at all.

## System design, if you're targeting SDE II or above

System design appears at SDE II and up, and occasionally as low-level design for SDE I and new grads. For new grads, expect class and interface modeling of a single bounded problem rather than a distributed architecture discussion. Recent reports include a car rental system, a railway booking system, a movie ticket booking flow, and a rate limiter — all LLD-shaped problems where the interviewer is watching how you decompose entities, constraints, and conflicts.

For SDE II and above, the questions tend to be grounded in Amazon's actual products, which makes preparation more targeted than generic "design Twitter" practice. Reported prompts include a distributed task notification service with retry and dead-letter queues, a chat application with video calling, a recommendation engine, a URL shortener, a file storage service with versioning and multipart upload, and search autocomplete with trie and ranking.

The scoring pattern is consistent: spend the first five to ten minutes on requirements and scale numbers before drawing anything. Interviewers ask for request rate, storage volume, and per-record size, and they grade failure handling — what happens when every locker is full, what happens when a message can't be delivered.

AlgoMonster's system design material is introductory. It covers load balancing, caching, and database sharding at a level that's useful background, not sufficient for an L5 loop. Plan on 20–40 hours elsewhere if system design is a scored round for your level.

The same goes for volume practice. AlgoMonster's problem set sits in the low hundreds, and candidates who pass top-tier loops at Google or Amazon almost always pair a pattern course with a larger bank for volume. Amazon's OA in particular is graded by hidden test cases, and passing them is a mechanical skill that improves with reps.

## A six-week schedule that fits the actual rounds

| Week | Focus | Concrete output |
| --- | --- | --- |
| 1 | Arrays, hash maps, two pointers, sliding window | 20 problems solved, each tagged with the pattern it used |
| 2 | Binary search, intervals, heaps / top-K | 15 problems, plus timed runs in Speedrun-style mode |
| 3 | Trees and graphs: BFS, DFS, topological sort | 20 problems including 5 grid problems |
| 4 | Dynamic programming | 15 problems, written up in your own words |
| 5 | LP stories + system design or LLD | 10 stories in STAR with numbers, 3 design write-ups |
| 6 | Mixed timed mocks, no execution environment | 2 problems per session in a plain editor, with the explanation spoken aloud |

Week 6 is the one people skip. Amazon's editor doesn't run your code, so practicing in an IDE trains a habit you can't use in the interview.

## Where AlgoMonster fits in this stack

AlgoMonster is a structured course, not a problem bank. The official page describes 500+ lessons across 6 courses, 1,000+ illustrations, and 3,000+ editorials, with unlimited AI assistant usage and a Speedrun mode for timed review. Real questions from top tech companies are included and refreshed monthly. Content is written by ex-Google engineers and competitive programmers.

Two details are worth calling out because they're unusual:

- The AI assistant is embedded rather than bolted on. It can explain selected content in plain language, and it will debug a submitted solution and point at the error instead of handing you the answer.
- The subscription bundles additional courses at no extra cost, including a CS foundations course and a "build an LLM from scratch" course covering tokenization, attention, and training.

Where it doesn't cover you:

- **No video.** Every explanation is text with interactive diagrams. If you learn by watching someone solve problems on screen, this format will feel dry and you'll retain less.
- **Limited system design.** Introductory material only.
- **Light behavioral content.** Not a substitute for real LP preparation.
- **No live mock interviews or mentorship.** Nothing simulates a senior engineer watching you and interrupting with follow-ups.

The honest read: AlgoMonster is a good fit if you can already write correct code in one language, your actual gap is *which approach to reach for*, and you have 4–8 weeks at 1–2 hours a day. It's a poor fit if you need programming fundamentals, or if system design and behavioral rounds are the ones standing between you and an offer.

Amazon's coding rounds reward exactly the skill this format trains — fast pattern classification before implementation. The parts of the loop AlgoMonster doesn't touch are also the parts you can prepare for with a notes file and a friend who'll interrupt you mid-sentence.

## AlgoMonster plans and current prices

The pricing page lists four options. Prices move with promotions, so confirm at checkout rather than trusting any third-party figure, including ones you find in reviews.

| Plan | What you get | Price | Billing | Get it |
| --- | --- | --- | --- | --- |
| Free | Limited access to a subset of patterns and problems | $0 | — | [Explore AlgoMonster's free content](https://algo.monster?fpr=li69) |
| Pro – Monthly | All patterns, lessons and problems; unlimited AI assistant; unlimited Speedrun; company question banks updated monthly; 1 month of access | $18.99/mo | Billed monthly, cancel anytime | [Compare the AlgoMonster monthly plan](https://algo.monster?fpr=li69) |
| Pro – Yearly | Everything in Monthly, plus 12 months of full access, member discount on live bootcamps, 500+ lessons across 6 courses, Foundation and LLM bonus courses | $69.99/year (listed as $5.84/mo) | Billed annually | [See AlgoMonster's yearly plan pricing](https://algo.monster?fpr=li69) |
| Pro – Lifetime | Everything in the annual plan plus lifetime updates, one-time payment | $89 | Billed once | [Check the AlgoMonster lifetime plan](https://algo.monster?fpr=li69) |

A note on those numbers. AlgoMonster runs discount campaigns frequently, and archived snapshots of the same subscribe page have shown a yearly plan at $99 and a lifetime plan at $189 during other sale windows. That means the figures above are the current listed prices, not a permanent floor or ceiling. Check the page before you buy — the gap between a sale and a non-sale purchase has been large enough to matter.

The monthly option deserves a mention because most comparison articles written about AlgoMonster insist it doesn't exist. It does, at $18.99. For a three-week sprint before an Amazon loop, that's the cheapest route to the pattern curriculum, and it costs less than one month of the platform it's usually compared against.

## Building the whole stack

Two months out from an Amazon loop, the realistic allocation looks like this:

- A pattern course for the classification skill (4–6 weeks)
- A larger problem bank for volume, especially grid and graph problems before the OA
- Your own LP document — 10 stories, STAR-framed, numbers attached, "I" throughout
- A separate resource for system design or LLD, depending on your level
- Two or three practice sessions in a plain editor with no compiler

The part candidates underrate is the last one. Amazon hands you a Livecode editor with no run button, and the follow-up questions arrive while you're still typing. Rehearsing that specific discomfort is worth more than another twenty problems.

If the pattern half is your bottleneck, 👉 [AlgoMonster's pattern curriculum and free tier](https://algo.monster?fpr=li69) is the cheapest way to test whether the text-and-diagram format works for how you learn. If it doesn't click in the free tier, it won't click at $89 either, and you've spent nothing to find out.
