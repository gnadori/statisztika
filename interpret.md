How to Use and Interpret Your R Analysis

This guide explains how to use the student_analysis.R script and what to look for in the results.

How to Use This

Save Files: Place both student_analysis.R and your 1zt.csv file in the same folder on your computer.

Open R: Open your R environment (like RStudio).

Set Working Directory: Set your R session's working directory to the folder where you saved the files.

In RStudio, you can do this easily: Session -> Set Working Directory -> To Source File Location.

Install Packages (First Time Only):

In the student_analysis.R script, find the lines starting with install.packages(...).

Un-comment them (remove the #) and run those two lines.

You only need to do this once. You can add the # back after.

Run the Script: Run the entire student_analysis.R script. The results and plots will appear in your console and plot panes.

How to Interpret the Results

The script will give you several plots and text outputs. Here is what they mean.

1. Student Scores Histogram

What it is: A bar chart showing the distribution of total scores for all students.

What to look for:

"Bell Curve" (Normal): A wide spread of scores centered in the middle. This is typical.

Skewed Left (Most scores are high): The test was likely too easy for this group.

Skewed Right (Most scores are low): The test was likely too hard, or the material wasn't mastered.

Bimodal (Two "humps"): This is a red flag! It often means you have two distinct groups in your class (e.g., those who "got it" and those who "didn't").

2. Item Difficulty Plot

What it is: A bar chart showing the average score for each item (from 0.0 to 1.0).

What to look for:

Bars near 1.0: These are easy items. Almost everyone got full credit.

Bars near 0.0: These are hard items. Almost everyone got low credit.

A good test has a range of difficulties, with most items falling between 0.3 and 0.9. Too many easy items don't differentiate students, and too many hard items can be discouraging.

3. Reliability Analysis (Text Output)

When you print(reliability_results), you'll see a lot of text. Focus on this line:

raw_alpha (Cronbach's Alpha): This is your Test Reliability score. It tells you if your test is measuring a single concept consistently.

> 0.9: Excellent

0.7 - 0.9: Good/Acceptable

< 0.7: Questionable.

< 0.6: Poor. The test is not reliable.

4. Item Discrimination Plot (The Most Important!)

What it is: This plot shows the r.drop value for each item. This value measures: "Do students who did well on the whole test also do well on this specific item?"

What to look for: This is how you find "good" and "bad" questions.

High Positive Bar (r.drop > 0.3): This is a GOOD item. It successfully discriminates between high- and low-performing students. Keep it.

Low Positive Bar (0.1 < r.drop < 0.3): This is an "OK" item. It works, but it could probably be improved.

Near Zero (-0.1 < r.drop < 0.1): This is a BAD item. Getting it right or wrong is random and has no relationship to what the student knows. It's "noise" and should be revised or removed.

Negative Bar (r.drop < -0.1): This is a VERY BAD item. It means your high-performing students are getting it wrong and your low-performing students are getting it right. The question is likely flawed, has the wrong answer key, or is extremely misleading. Review this item immediately.

By looking at the Discrimination (r.drop) and Difficulty plots, you can make informed decisions about which items to keep, revise, or discard for future tests.
