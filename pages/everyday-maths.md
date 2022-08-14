# Everyday Maths

_Epistemic status: work in progress_

A collection of mathematical concepts that will help you navigate the deep, dark, murky digital ocean (and maybe the real one too). I hope I can explain these ideas in ways that anyone will understand.

- correlation does not imply causation
- multiple factor analysis
- Bayes rule
- functions
- stacks and queues
- everything is graphs
- theories of value
- compound interest
- equilibria
- objective functions
- probability and risk
- priors and stereotypes

## Categories and continuums

There are two types of data: categorical and continuous. **Categorical data** can be separated into discrete bins (or categories), such as a light switch being on or off, or days of the week. **Continuous data** can be any point on a line, such as height and weight, temperature, or the passage of time.

That's all well and good, but let's look at a real world example: biological sex. We generally think of sex as a binary category, male or female, which is determined by whether a person has XY or XX chromosomes. This model seems to be correct most of the time... but there are interesting exceptions. Some people have only one sex chromosome, or three of them. On top of that, you can alter the levels of certain hormones in your body -- i.e. testosterone and estrogen -- which are continuous quantities by the way -- to become "more male" or "more female".

You probably weren't expecting a page about everyday maths to swerve towards a hot-button political topic. But that is exactly why these concepts are so useful -- they will help you to understand and think critically about the world in which you live, in all aspects. You can use these ideas, like the dichotomy of categorical data and continuous data, to reason about a basic maths problem or to better understand a complex social issue.

So, what about biological sex? Must we conclude that sex is actually a spectrum, that male and female are arbitrary constructs? I don't know if math can provide us with a definitive answer; your answer will likely come from your own values. Personally, I think male and female are real things. They may not be strict categories like a light switch being on or off, but they represent the vast majority of people. In other words, I see it as a bimodal distribution. More on that later.

## Distributions

The world is a myserious place, and there are many things that we don't understand. Despite everything we have discovered up to this point, if anything we have only become more aware of how litle we know. In other words, we live with a great deal of uncertainty, and until we discover the One True Law of Everything, we need a way to manage uncertainty. So, we came up with the idea of distributions.

When you flip a coin, you don't know which side you'll get. You could try to use physics model it down to the last detail, like which side it starts on, the orientation of your hand, how you flip it, the effect of gravity and wind, and so on, until you can predict the outcome. But you don't want to do that.

On the other hand, you do know that the outcome will be either heads or tails, and that they have roughly the same chance. In other words, there are two possible outcomes, each with a probability of 1/2, so the total probability is 1. That's a distribution!

A coin flip is an example of a **categorical distribution**. Another example is a six-sided die: the outcome can be 1, 2, 3, 4, 5, or 6, and each outcome has a probability of 1/6. Similarly for other kinds of dice (for all you D&D nerds out there). And unless these coins and dice are weighted, they're also **uniform distributions** because every outcome has an equal probability.

Have you ever seen a "bell curve"? You might have seen it in school while talking about the grades everyone got on a test. Usually, a few students do really well, a few students do really poorly, and everyone else gets a grade somewhere in the middle. This is also a distribution, and it's called a **normal distribution**. Normal distributions can found all over the place. Aside from test scores, other examples include height, shoe size, and birth weight. Normal distributions are so common that many statistical techniques are based on the assumption that the variables under test are "normally distributed".

Not everything is normally distributed though. There is a lesser known distribution that also shows up everywhere: the **Pareto distribution**, also known as the "80/20 rule". This rule states that 80% of outcomes are caused by 20% of causes. For example:

- 80% of people live in 20% of the world's cities
- 80% of wealth is owned by 20% of people
- 80% of software errors are caused by 20% of software defects
- 80% of health care resources are used by 20% of people
- 80% of crimes are committed by 20% of people
- 80% of a company's revenue comes from 20% of its products

Now, these phenomena may not be exactly 80/20, and they may only apply under certain conditions, but the general idea is the point.

The Pareto principle is a very powerful idea, because when applied correctly, it can actually help you make decisions in your life. If 80% of your productivity comes from only 20% of the things you spend time on, then maybe you should focus more on that 20%. If 80% of the wealth is owned by 20% of the population, then the top 20% should be paying (at least) 80% of taxes. Now there's a hot political take!

## Hidden variables

Sometimes, the relationship between a cause and an effect might be different depending on the situation. For example, earlier I gave height as an example of a normal distribution. Clearly, if you collect the heights of everyone from babies to seniors, you won't get a bell curve, because people get taller as they get older. But, if instead you separate the data by age, then you'll see a bell curve within each age group. A statistician might call this **disaggregation**, "removing a confounding variable", or "controlling for age". Basically, you need to watch out for hidden variables when you're trying to understand the relationship between two things.

Here's a trickier example. I also said earlier that the top 20% should pay 80% of taxes. Actually, they already do, more or less. However, just because the wealthiest people pay the majority of all taxes, doesn't mean that the tax regime is fair. What matters is whether everyone across the board pays the same _rate_ of taxes based on their income. In other words, we need to separate out the tax data by income, and see if the tax rate is constant. If you do this analysis, you will find that the wealthy pay a much lower tax rate than everyone else. There are many reasons, but it is primarily because the wealthy receive most of their income from investments, which are taxed at lower rates and often qualify for more tax deductions than income from a job. In this case, the _tax law itself_ was a hidden variable.
