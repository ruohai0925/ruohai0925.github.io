---
layout: post
title: "The Second Half of Computational Fluid Dynamics"
date: 2026-02-17
author: Ruohai
permalink: /The-Second-Half/
---

## Education and Industrial Application

> **tldr:** AI will reshape the education and various industrial applications of Computational Fluid Dynamics, from code development to human-computer interaction.

In April 2025, Shunyu Yao, then a researcher at OpenAI, published an article titled [*The Second Half*](https://ysymyth.github.io/The-Second-Half/). Now, on February 17, 2026—approximately a year and a half later—I have profoundly felt the potential and massive impact of AI on my industry, **Computational Fluid Dynamics (CFD)**. This realization compelled me to write this article.

I believe the development of AI has never been linear. When Shunyu wrote "The Second Half," AI's capabilities might have primarily influenced the field of computer science. However, after a year of accumulation and radiation, I believe it has now arrived at the doorstep of my industry.

Recording this moment has special significance. First, while driving for groceries or commuting, I utilized fragmented time to listen to a recent [two-and-a-half-hour interview with Shunyu](https://www.youtube.com/watch?v=gQgKkUsx5q0). Furthermore, just the week before last, on February 5, 2026, Anthropic released its new model, [Claude Opus 4.6](https://www.anthropic.com/news/claude-opus-4-6). I used it to solve a thorny problem at work and deeply felt its power. I couldn't wait to share this feeling with everyone. Unfortunately, as it coincides with the Chinese Lunar New Year, most people are enjoying reunions, and few are inclined to discuss such serious topics during the holidays. Thus, I write these words as a review of my old year and a revelation for the new one.

## The First Half

**Computational Fluid Dynamics (CFD)** is essentially a branch of fluid mechanics, a very ancient discipline. Starting with early physicists like Newton and Prandtl, countless pioneers poured their hearts and blood into attempting to understand, explain, apply, or summarize natural phenomena and principles. Gradually, fluid mechanics formed three research approaches: *experiment*, *theory*, and *computation*.

Driven by research and application needs, CFD [emerged in the 1930s and 40s](https://en.wikipedia.org/wiki/Computational_fluid_dynamics). Through the continuous exploration of numerical schemes by groups of mathematicians and physicists, they solidified the classic and fundamental methods we use in the solving domain today (such as the numerical solution of Navier-Stokes equations) to explain and predict natural phenomena. For example, we can use CFD to calculate the aerodynamic performance of an F1 race car or to explain why airplanes can fly.

Based on the sedimentation of this knowledge, major companies have mastered their own commercial products, such as [FLUENT](https://www.ansys.com/products/fluids/ansys-fluent), [STAR-CCM+](https://www.siemens.com/en-us/products/simcenter/fluids-thermal-simulation/star-ccm/), and [Fidelity](https://www.cadence.com/en_US/home/tools/system-analysis/computational-fluid-dynamics.html). These products help customers perform simulations before manufacturing real objects, thereby saving costs and providing optimization solutions. Of course, open-source software like [OpenFOAM](https://www.openfoam.com/), [SU2](https://su2code.github.io/), and [FEniCS](https://fenicsproject.org/) has also supplemented this community.

In the field of education, our current stage is still solidified in using textbook knowledge, supplemented by simple programming, to help students understand fluids and the underlying mathematical principles. There is a clear gap between fluid dynamics educators and practicing industrial engineers: the former lean more towards basic research and, frankly speaking, most do not always directly generate real economic benefits or value; the latter use engineering software to solve problems and, unless necessary, usually do not delve into areas that are not yet fully understood (such as the underlying mechanisms of turbulence models).

Finally, sitting between large corporations and the education sector is a series of startups. They are creating their own industrial software to solve specific problems or engaging in outsourcing, sales, and customer service related to CFD.

## The Second Half

Like Shunyu, after graduating with my Ph.D., I worked in industrial software companies for many years. I know very clearly where the barriers and ceilings of current CFD software development lie. Without the empowerment of AI, we might still be in a role allocation where "big companies eat meat, and small companies drink soup," living in harmony. However, the emergence of AI is reshaping every process of industrial development.

To give a simple example: friends in our industry might think that because of the profundity of fluid dynamics, the complexity of turbulence knowledge, and the pain paid in learning partial differential equations, we have accumulated deep *Domain Knowledge*, and thus AI will not replace us soon. I personally disagree with this view. In fact, no matter how experience-dependent this knowledge is, it can essentially be solidified and learned.

As mentioned in the introduction, I used AI to solve a practical problem that had plagued me, an engineer, for a long time. AI was able to point out the core of the problem instantly. **I have to admit, it is better than me.**

We can envision the future: suppose we want to develop a set of industrial codes. The internet today actually has all the necessary "raw materials"; what is lacking is a role that can efficiently integrate these materials and maximize their value. Previously, a practitioner might only know the solver, another only the frontend UI design, and a third only backend post-processing. They would combine to form a team. Even if a team is formed, mere information exchange is laborious. However, with the development of AI, especially the recently released [Claude Opus 4.6](https://www.anthropic.com/news/claude-opus-4-6) and [GPT-5.3-Codex](https://openai.com/index/introducing-gpt-5-3-codex/), it can already read hundreds of thousands of lines of code and extract the most critical information. Like finding a needle in a haystack, it can find the most important raw materials to help people rapidly iterate designs, develop prototypes, and fix defects. Especially with recent *Agent Teams*, **one person can function as a whole team**. What is "scary" is that AI is currently training AI—a strong alliance. The speed of iteration and evolution of silicon-based life is far greater than that of humans as carbon-based life. As someone who only started learning to swim as an adult, I have a deep appreciation for this difference.

It seems that small companies can actually carry out the reconstruction of large-scale industrial software with streamlined personnel. The difficulty lies in whether they can snatch customers from big companies. Although big companies have redundant personnel and their territories are being encroached upon, their advantage lies in possessing massive internal data for AI to train and learn from. Regarding the future competitive landscape, I don't think there is a definite endgame; both small and large companies will exist, but both will be extremely streamlined. Yes, I mean my rice bowl (job) might be gone soon. HRs and managers still hiring, please pay attention to me; my GitHub is: [github.com/ruohai0925](https://github.com/ruohai0925) :)

Listening to Shunyu's podcast, a word he and the host mentioned repeatedly was *"Value."* This is especially true in the CFD industry. Whoever can generate value for customers and the field, and bring economic benefits, will dominate the product, the cycle, and even the future of the industry. So, we need to stop and think: Where is the real value of the CFD industry?

> There used to be a saying, *"talk is cheap, show me the code."* I think it will become, ***"code is cheap, show me the value."***

In terms of CFD education, the impact of AI is even more self-evident. Parts previously considered deep numerical computation and simulation coding can now be easily and quickly completed by AI. I want to give a long-range example: when we were in school, what improved our practical ability the most was often doing one "hardcore" project after another. The appearance of AI provides an opportunity; it can help us design a rigorous, step-by-step, clearly explained teaching chain. Through such a learning strategy—perhaps 100+ steps of "advancing gradually and entrenching at every step"—a person can build an *End-to-End* ultra-long project from scratch. Its difficulty may have surpassed the syllabus that current university professors can design, but at the same time, it has infinite knowledge to feed back to students, allowing them to get timely help when encountering problems. Instead of teaching students in categories—this is the shell material, this is the mathematical equation, this is the aerodynamic principle—AI directly says: *"Let's build a small rocket together, hand in hand."* [Andrej Karpathy](https://github.com/karpathy)'s contribution to the field of Large Language Model education was guiding everyone to build a GPT from scratch. With the development of AI, CFD and other industries will also see their own Andrej Karpathys.

In this sense, just as many universities have been vigorously cutting certain majors recently, the teaching mode in the field of fluids will also change—whether it is personnel, textbooks, or the entire organization of learning. If AI can explain things more clearly than a teacher, then the value of the teacher's existence (and even the university as a way of organizing higher education) is open to question.

## Summary

It is observed that engineers and researchers within OpenAI and Anthropic may now spend 70–80% of their time writing code using AI. This situation will gradually radiate to industrial software companies. The only remaining advantage I can think of is that we engineers in the CFD industry possess a certain *Context*. In the process of interacting with AI, compared to outsiders, we can provide better *Prompts* and context information in a short time—like chanting spells, we know one or two more lines that can unlock high-level magic than ordinary people. But my personal feeling is that this advantage will not last too long. The so-called "spells" of an industry will eventually be open-sourced or free in the future, regardless of whether the creator is a human or AI.

Another line of defense that may not be breached in the short term is *Interaction* in industrial software. After all, industry serves people, and it requires communication between people. Engineers need to act as agents for customers to familiarize themselves with software, solve problems, and explain the meaning of reports. These interaction tasks will still need to be done by humans in the future, but the efficiency will be greatly improved—work that previously required 5–10 people might now only need 1–2.

In any case, I believe that the education and industrial application of Computational Fluid Dynamics have entered **The Second Half**. Just as eating and sleeping are necessities for us, using AI daily, keeping up with its changes, understanding its capabilities, and carefully thinking about the positioning of practitioners within it is an urgent and necessary matter. I hope we can learn and apply AI together with friends in the industry, exploring its boundaries and using it to broaden the boundaries of the industry.

---

*February 17, 2026*
