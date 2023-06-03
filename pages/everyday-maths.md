# Everyday Maths

*Rules for a Data-Driven Life*

*Epistemic status: work in progress*

A collection of mathematical concepts that will help you navigate the deep, dark, murky digital ocean (and maybe the real one too). I hope I can explain these ideas in ways that anyone will understand.

## Bayes rule

TODO: sometimes prior assumptions (stereotypes) are useful

## Categorical and continuous

There are two kinds of data: categorical and continuous. **Categorical data** can be separated into discrete bins (or categories), such as a light switch being on or off, or days of the week. **Continuous data** can be any point on a line, such as height, weight, temperature, or the passage of time.

This dichotomy is nice and clean, so let's consider a real-world example that breaks it: biological sex.

Sex is generally considered a binary *category* -- male or female -- which is determined by whether a person has XY or XX chromosomes. But some people have only one sex chromosome, or three of them. Furthermore, you can alter the levels of certain hormones in your body -- i.e. testosterone and estrogen, which are *continuous* quantities -- to become "more male" or "more female".

What do we do with this? Maybe sex actually isn't a category, male and female are just arbitrary concepts, and we should discard the whole thing because it just makes people feel bad about themselves. Maybe male and female are meaningful categories, albeit with some interesting outliers, and we should definitely appreciate the differences between them if we want the human species to continue. Maybe you weren't expecting a page about "everyday maths" to quickly swerve towards such a contentious political topic.

Messy concepts like biological sex are exactly why the concept of data is so useful. They will make you think critically about the world in which you live. Rather than make the world fit into clean models, seek models that fit the world in all its messiness. Use these ideas to reason equally about a simple maths problem or a complex philosophical question.

And as for biological sex, hopefully you can tell from how I worded the various possible conclusions, which one I hold.

## Compound interest

TODO: you can benefit from it, or it can benefit from you

## Correlation and causation

TODO: correlation does not imply causation

## Distributions

The world is a mysterious place, and there are many things that we don't understand. Despite everything we have discovered up to this point, if anything we have only become more aware of how little we know. In other words, we live with a great deal of uncertainty, and until we discover the One True Law of Everything, we need a way to manage uncertainty. So, we came up with the idea of distributions.

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

## Equilibrium

TODO: some are stable and some are unstable, learn how to tell the difference

## Functions

TODO: any action can be described as a function, if you have a hard time understanding how something works, try to describe it as a function, what are its inputs? what are its outputs?

## Graphs

TODO: everything is a graph, if you have a hard time understanding a thing, try to describe it as a graph

## Hidden variables

Sometimes, the relationship between a cause and an effect might be different depending on the situation. For example, earlier I gave height as an example of a normal distribution. Clearly, if you collect the heights of everyone from babies to seniors, you won't get a bell curve, because people get taller as they get older. But, if instead you separate the data by age, then you'll see a bell curve within each age group. A statistician might call this **disaggregation**, "removing a confounding variable", or "controlling for age". Basically, you need to watch out for hidden variables when you're trying to understand the relationship between two things.

Here's a trickier example. I also said earlier that the top 20% should pay 80% of taxes. Actually, they already do, more or less. However, just because the wealthiest people pay the majority of all taxes, doesn't mean that the tax regime is fair. What matters is whether everyone across the board pays the same *rate* of taxes based on their income. In other words, we need to separate out the tax data by income, and see if the tax rate is constant. If you do this analysis, you will find that the wealthy pay a much lower tax rate than everyone else. There are many reasons, but it is primarily because the wealthy receive most of their income from investments, which are taxed at lower rates and often qualify for more tax deductions than income from a job. In this case, the *tax law itself* was a hidden variable.

## Multiple factor analysis

TODO: a thing rarely has only one cause

## Objective functions

TODO: we are all driven by goals and objectives, whether we realize it or not. what objective function are you trying to optimize?

## Probability and risk

TODO: everything we do carries risk, but how do we decide whether something is "too risky"? it can be useful to compare things with similar risk to keep our brains in check

## Stacks and queues

TODO: we all work towards goals, but how do we prioritize each task?

## Theories of value

TODO: is it the cost of production? or is it what people are willing to pay? learn how to tell how someone is trying to value you
