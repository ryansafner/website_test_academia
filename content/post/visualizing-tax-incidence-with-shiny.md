---
categories:
- rstats
- teaching
comments: true
date: 2018-10-07T18:35:00
tags:
- rstats
- shiny
- teaching 
- economics
title: Visualizing Tax Incidence with Shiny
---

As I have mentioned in [other posts](https://ryansafner.com/post/visualizing-linear-regression-with-shiny/), this semester I trying to maximize the number of intuitive visualizations for my students to master economic and mathematical concepts more in my teaching, as well as develop my own `R` skills. For my [intermediate microeconomics course](http://ryansafner.com/courses/econ306), I recently put together an  [interactive Shiny App](https://ryansafner.shinyapps.io/tax-incidence/) with `R` that demonstrates the effect of a tax on consumers and producers.

Simply input your own (inverse) demand and supply functions and the size of the tax, and the graph and summary will update with the market equilibrium and the surpluses lost by the tax. This will allow students to see several effects that we commonly teach in microeconomics:[^1] 

1. **The economic burden of the tax depends on the relative price elasticities of demand vs. supply.** Whomever is mandated to pay by statute may not end up being the party that bears the entire tax. Whomever has a greater elasticity (demand or supply) will bear *less* of the tax, and vice versa. I teach my students to think of "elasticity" as being equivalent to one's ability to "escape" a tax. The Shiny apps shows that simply *increasing* the slope parameter of Supply or Demand will *lower* its' elasticity, and *raise* the share of the tax borne by that side of the market.   
    
2. **Larger taxes lead to larger market distortions.** Tax revenue increases at a rate less than $t$ and deadweight loss increases at a rate greater than $t$. Simply increase the tax rate and see how government revenue changes and deadweight loss changes. This is why economists call for "low rates and broad bases."
    
The visualization can also show the effects of extremes: perfectly elastic demand or supply (simply set $slope=0$). **A perfectly elastic curve bears none of the tax and shifts it entirely to the other side of the amrket.** The calculated burden for that party will be 0, and the other party's share will unfortunately mess up to read $"NaN\%"$,[^2] but this is to be interpretted as $100\%$. The visualization cannot show the effect of perfectly *inelastic* demand or supply (vertical lines) since I cannot set a slope slider value to be $\infty$. 

To give credit where it is due, I was originally inspired by [this visualization](http://home.uchicago.edu/cbm4/econ260/E260tidemo.html) apparently made in Mathematica for Casey Mulligan's [Public Finance class](http://home.uchicago.edu/cbm4/econ260/) at the University of Chicago. 

[^1]: For more on the economics, see Lecture 10 slides on this topic from the course page.

[^2]: This is since I calculated each share according to the common formula: $\frac{|\text{elasticity of other party}|}{(|E_D|+E_S)}$. If instead I had calculated the change in Consumer Surplus and change in Producer Surplus, we could get accurate numbers.