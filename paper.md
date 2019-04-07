---
title: 'Multi-attribute task builder'
tags:
  -	multi-attribute decision task
  -	online experiment
  -	JavaScript
authors:
  -	name: Yury Shevchenko
orcid: 0000-0002-3397-8465
affiliation: 1
affiliations:
  -	name: University of Mannheim, Germany
index: 1
date: 26 March 2019
bibliography: bibliography.bib
---

# Summary

The multi-attribute task is a framework used by social scientists to study decision-making processes. In a typical experimental setup, a participant must select one of the options in each trial. The options differ in their attribute values, which are presented in a table format (see Figure 1). This paradigm allows researchers to explore what decision strategies people use, how they search and aggregate available information. In addition to the actual choices, a researcher can analyze process parameters such as response times and information search trajectories.

Figure 1: The movie task

![The movie task](https://raw.githubusercontent.com/Yury-Shevchenko/mad/master/images/Example%201.png)

The multi-attribute decision paradigm in a tabular format was described as "Mouselab" in the book by Payne, Bettman and Johnson "The adaptive decision maker" [@Payne1993]. Since then, it has been a popular approach for investigating decision processes. Following the general guidelines, researchers developed their own laboratory versions of Mouselab tailored to their needs [@Jasper2002, @Reisen2008]. Nevertheless, due to differences in software and programming languages, it was difficult to share tasks within the research community.

Willemsen and Johnson developed MouselabWEB as an online version of Mouselab [@Willemsen2010a]. MouselabWEB supports HTML and JavaScript and has been available online for many years since its release [@DanGoldstein2006]. However, there is a clear need for modern applications that help researchers design and publish their own Mouselab tasks online with greater flexibility and usability.

We present the Multi-Attribute Decision (MAD) builder for creating a Mouselab task in an online experiment. The MAD builder is available as a template in [lab.js](https://labjs.felixhenninger.com/), free and open-source software. The task builder is also accessible at [Open Lab](https://open-lab.online), an online platform for deployment of experiments.

MAD builder gives a researcher control over many parameters such as the display of the task, randomization algorithms, feedback options, and presentation of cues as text or images. Saved as a JSON file, MAD builder file can be easily archived or shared among researchers. The user manual for the task is available on the [GitHub page](https://github.com/Yury-Shevchenko/mad). The manual describes how to customize the task by changing task parameters. It presents four usage scenarios with different types of content and information presentation strategies. At the end, the manual shows how to work with the data generated in an experiment.

The tabular format of the multi-attribute decision task has prevailed in previous process-tracing studies [@Willemsen2010a]. The MAD builder allows the construction of tables of different sizes and positioning options either in the top row or in the left column. The builder has been already used for the design of experimental tasks in several studies on decision-making [@ScharfS, @Shevchenko2018].

The presentation of information in tables, however, limits the scope of research questions to the analysis of how people deal with structured information. Researchers may be interested in learning how people behave in other contexts that employ a more ecologically valid design in which information about cues is scattered around and embedded in the environment. New research questions can be asked in this case, such as how do people organize available information [@Ettlin2015]. The MAD builder allows the user to fully customize the display of options and cues by positioning them in any place on the screen. In this way, participants can interact with images of objects and examine their attributes and values by clicking on them (see Figure 2).

Figure 2: An example of the task with cues embedded into the image. The cue values can be examined by clicking on them.

![The bicycle task](https://raw.githubusercontent.com/Yury-Shevchenko/mad/master/images/Example%204.png)

# References
