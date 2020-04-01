On 25 March, the NYT published an [op-ed by Nicholas
Kristof](https://www.nytimes.com/interactive/2020/03/25/opinion/coronavirus-trump-reopen-america.html)
arguing in favor of social distancing. I am all in favor of social
distancing, since it does give a chance for the healthcare system to
adapt to this emergency and for scientists to develop a vaccine.

However, the "social distancing for 2 months" graph in Kristof's piece
had a strange exponential-looking uptick right at the end, and in the
piece itself he admits:

> A skeptic will note that these measures don’t seem to prevent a surge
> in infections so much as delay them (in some cases so that the impact
> is pushed beyond the period that this model tracks). There’s something
> to that: We may see a resurgence whenever we let up, at least until we
> have a vaccine or herd immunity.

Later, a co-worker pointed me to an excellent Medium article, [A call
to honesty in pandemic modeling
](https://medium.com/@wpegden/a-call-to-honesty-in-pandemic-modeling-5c156686a64b),
by M.Chikina (bioinformatician at University of Pittsburgh
School of Medicine) and W. Pegden (mathematician at Cargie Mellon), in
which they argue that Kristof's selective use of data hides the fact
that social distancing (at least without further developments, such as
a vaccine or new treatments) will simply postpone a spike in cases.

I have a lot of respect for Kristof, so his weird data sleight-of-hand
drove me into a rathole of Javascript reverse engineering. In the end,
thanks to the excellent [source
overrides](https://developers.google.com/web/updates/2018/01/devtools#overrides)
feature of the Chrome developer console, I was able to edit the model
in Kristof's article and reproduce Chikina's and Pegden's results.

The code in this directory is a copy of the [NYT
model](https://static01.nyt.com/newsgraphics/2020/03/16/opinion-coronavirus-model-2/d268775237c095931fe2fae6015c568c0011fd76/build/js/main.js),
modified to double the number of simulation steps (`overallN`) and
extend the end of the simulation from 2020-10-25 to 2021-08-21.

The image in this directory is a screenshot of the result, and shows
what happens to the uptick at the end of Kristof's truncated graph.

Conclusion? This model does not take into account the development of
vaccines or better treatments. Today we probably do not have a better
option than isolation. I will continue to stay indoors and follow
advice from public health experts. But we need honesty from public
figures, and Kristof's readers deserve a clarification and an apology.
