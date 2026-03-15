---
title: Error Estimation in Filtration Experiments
date: '2025-04-12'
categories:
  - discussion
tags:
  - experiment
  - analysis
  - error
slug: error-estimation
---

My colleagues and I occasionally receive this question from reviewers: **How many time have the authors repeated the experiment?**

There are several ways to answer, depending on what have been done: *"We repeated each experiment three times, and we plotted the average values and slapped some error bars that cover the maximum as well as minimum values. Most of the error bars are small, except at this position Z the error bar is humongous -- there we obtained results that were quite spread out, and we have no idea why."*

Or, something like: *"We did not repeat any experiment because we have run out of resources."*

Of course the wording is different. But, if the answers end there, the authors miss ***the point*** of the reviewers. To my understanding, the question being implied is: **How far are you from the *true* values?**

True values are hypotherical. What we process engineers can obtain, with a masterpiece of experimental control and through many repetitions, are called the **best estimated values**. The experiments -- however careful we are at conducting them -- are *imperfect*. And we, the authors, need to explain that **we are confident that our values are close to what they should be (the real values)**, and hence, **our results can be trusted**.

This is not easy.

Of course, one repetition gives less confidence than three repetitions, and three repetitions give less confidence than, say, forty repetitions.

With forty repetitions, the values obtained will probably form a Gaussian distribution -- the spread of this distribution takes into account all experimental variability: material non-uniformity, changes in surrounding environment, human inconsistency, analytical error, *etc.* The mean value may be considered as the best estimated value -- the true value may lie somewhere within the standard deviation range. This makes sense.

After forty repetitions per data point, the authors (who are, of course, process engineers) can proudly response to the reviewers, something like this:

*"We have account for all the error sources and illustrate them graphically, with the standard deviations presented as error bars. Forty repetitions have been performed per data point, and there are 50 unique data points in this paper, hence we have conducted a total of **2000 day-long experiments**. As a result, this paper is already 8 years in preparation. Three PhD students have been working on this paper -- one had quit after 3 years due to frustration, another one had been kicked out after 6 years due to the lack of funding -- anyway, our results are quite believable right now."*  

Jokes aside, we have neither time nor resources to repeat each experiment 40 times. To answer the reviewer's tricky question, we have to be *smart*. And, by the way, **three repetitions are not enough**.

Figure 1 gives an example: the pure water permeability of a commercial membrane obtained from 42 experiments. The permeability is an intrinsic membrane property, which indicates how easy water can pass through the membrane. Permeability measurement is not a day-long experiment -- it is only between 30 and 60 min. So, our group (IAMT-KIT) always do this step to control the membrane quality before each 'main' experiment.

![Permeability error](/16-04-25_Fig_1.svg)

*Figure 1. Variation of the mean (grey circles) and standard deviation (green diamonds) with the number of repeated permeability measurements. Error bars represent the standard deviations. Adapted from [Imbrogno et al. (2024)](https://doi.org/10.1016/j.chemosphere.2024.141833) -- basically reprinted but with some colour touch-up.*

Imagine the below situations.

- With over forty repetitions, the mean value obtained, let's say by researcher A, is 14.9 L/m<sup>2</sup>.h.bar, and the standard deviation is 2.0 L/m<sup>2</sup>.h.bar. The true permeability of the membrane should lie somewhere between 12.9 and 16.9 L/m<sup>2</sup>.h.bar.

- Imagine now that researcher A only measures the membrane permeability three times and calls it a day. Researcher A has only the three left-most square symbols in Figure 1 (16.6, 17.9, and 17.2 L/m<sup>2</sup>.h.bar). The average value is 17.2 L/m<sup>2</sup>.h.bar, and the error bar is 0.6 L/m<sup>2</sup>.h.bar. The true value is, likely, below the range obtained from only three repeats (16.6 -- 17.8 L/m<sup>2</sup>.h.bar). In A's report, the membrane permeability is overestimated.

- New student C carries out one permeability measurement for the same membrane, and obtains a permeability of 12.7 L/m<sup>2</sup>.h.bar (the star symbol in Figure 1). This value is lower than the permeability range obtained from only three repeats (17.2 ± 0.6 L/m<sup>2</sup>.h.bar), so the student gets complained (by researcher A) for a bad experiment. However, if there have been 42 data points of permeability, student C's value is well within the 95% confidence interval; some of the 42 data points are even more off. So the experiment done by C is actually good!

The above discussions just emphasize that it is important to repeat experiments many times. So, what is the smart way to get around that?

Here is the smart way.

**We do not repeat any experiment, and we just estimate the error bar, *but* the true value -- or the best estimated value had we repeated the experiments 40 times -- *should* lie within the error bar that we estimate.** 

See the error bar of the star symbol in Figure 1? This error bar was estimated, and there is a good chance the true value lies within this error bar -- this is more or less confirmed from the 42 permeability measurements. 

The ultimate goal of error estimation is, one data point (e.g., the star symbol) accompanied by a well-estimated error bar can replace forty data points from repetition (e.g., the square symbols).

Good error estimation must require two important ingredients: **common sense** and **experience**. Experience is to find the link between different types of experimental variability and the target parameter. Common sense is to avoid complicated and needless calculations.

The concepts of error estimation are not easy to explain and should be accommanied by examples. My colleagues and I published [a paper in Chemosphere Journal](https://doi.org/10.1016/j.chemosphere.2024.141833) to discuss that in 19 pages, with a number of case studies. You can check it out to learn more about error estimation. Below are some bullet points drawn from the paper.

- Some error sources contribute more (i.e. have more **'weights'**) to the target parameter (let's call it parameter T) than other error sources. The important error sources should be kept in error estimation. The unimportant error sources can be omitted to simplify.

- If a particular error source has a very strong weight, the relative error of parameter T should be roughly equal to the relative error of that error source. If there are multiple error sources with more or less equally strong weights, **error propagation** can be applied to calculate the error of parameter T. 

- Error estimation will not sound convincing to some reviewers -- this is expected. To validate the error bars, we suggest selecting ONE experiment and repeat it five times. **The five data values should lie within the error bar estimated for one of the values.** If not, error estimation needs to be revised. Experience is needed in choosing which experiment to repeat.