---
layout: lesson
root: .
permalink: index.html
---


> ## Prerequisites
>
> You need to understand the concepts of **files** and **directories** and how to start a Python
> interpreter before tackling this lesson. This lesson sometimes references Jupyter
> Notebook although you can use any Python interpreter mentioned in the [Setup][lesson-setup].
>
> The commands in this lesson pertain to **Python 3**.
{: .prereq}

### Getting Started
To get started, follow the directions on the "[Setup][lesson-setup]" page to download data
and install a Python interpreter.

{% include links.md %}

> ## Event
>
> This lesson guides you through the basics of file systems and the
> shell.  If you have stored files on a computer at all and recognize
> the word "file" and either "directory" or "folder" (two common words
> for the same thing), you're ready for this lesson.
>
> If you're already comfortable manipulating files and directories,
> searching for files with `grep` and `find`, and writing simple loops
> and scripts, you probably want to explore the next lesson: [shell-extras](https://carpentries-incubator.github.io/shell-extras/).
{: .prereq}

## General Information

This Software Carpentry workshop is sponsored by UCF Office of Research and conducted by the [RCI](https://rci.research.ucf.edu/) team. Software Carpentry aims to help researchers get their work done in less time and with less pain by teaching them basic research computing skills in a supportive & inclusive environment. This hands-on workshop will cover basic concepts and working with the Unix shell.

**Who:** This workshop is aimed at graduate students and other researchers, but all are welcome to attend. This is a basics level workshop for an audience who intend to start working with Unix in the future. You don't need to have any previous knowledge of the tools that will be taught.  

**Where:** This training will take place online. The instructors will provide you with the information you will need to connect to this meeting.

**When:** 10:00am - 4:30pm ET, 11 March 2021

**Description:** This lesson teaches novice programmers to write modular code to perform data analysis using Python. The emphasis, however, is on teaching language-agnostic principles of programming such as automation with loops and encapsulation with functions, see [Best Practices for Scientific Computing](https://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1001745) and [Good enough practices in scientific computing](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005510) to learn more. The example used in this lesson analyses a set of 12 files with simulated inflammation data collected from a trial for a new treatment for arthritis. Learners are shown how it is better to automate analysis using functions instead of repeating analysis steps manually.

**Prerequisites:** This lesson guides you through the basics of file systems and the shell.  If you have stored files on a computer at all and recognize the word "file" and either "directory" or "folder" (two common words for the same thing), you're ready for this lesson. If you're already comfortable manipulating files and directories, searching for files with `grep` and `find`, and writing simple loops and scripts, you probably want to explore the next lesson: [shell-extras](https://carpentries-incubator.github.io/shell-extras/).

**Requirements:** Participants must have access to a computer with a Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed below).

<!--Accessibility: We are dedicated to providing a positive and accessible learning environment for all. Please notify the instructors in advance of the workshop if you require any accommodations or if there is anything we can do to make this workshop more accessible to you.-->

**Registration:** Please register [here](EventBrite Link). Event registration is free. There are a limited number of seats and available on a first come, first served basis.

**Contact:** Please email <ResearchIT@ucf.edu> for more information.

### Arthritis Inflammation
The best way to learn how to program is to do something useful, so this introduction to Python is built around a common scientific task: **data analysis**. We are studying **inflammation in patients** who have been given a new treatment for arthritis, and need to analyze the first dozen data sets of their daily inflammation. The data sets are stored in [comma-separated values]({{ page.root }}/reference.html#comma-separated-values) (CSV) format:

- each row holds information for a single patient,
- columns represent successive days.

The first three rows of our first file look like this:
~~~
0,0,1,3,1,2,4,7,8,3,3,3,10,5,7,4,7,7,12,18,6,13,11,11,7,7,4,6,8,8,4,4,5,7,3,4,2,3,0,0
0,1,2,1,2,1,3,2,2,6,10,11,5,9,4,4,7,16,8,6,18,4,12,5,12,7,11,5,11,3,3,5,4,4,5,5,1,1,0,1
0,1,1,3,3,2,6,2,5,9,5,7,4,5,4,15,5,11,9,10,19,14,12,17,7,12,11,7,4,2,10,5,4,2,2,3,2,2,1,1
~~~
{: .source}
Each number represents the number of inflammation bouts that a particular patient experienced on a
given day. For example, value "6" at row 3 column 7 of the data set above means that the third
patient was experiencing inflammation six times on the seventh day of the clinical study.

So, we want to:

1. Calculate the average inflammation per day across all patients.
2. Plot the result to discuss and share with colleagues.

To do all that, we'll have to learn a little bit about programming.
