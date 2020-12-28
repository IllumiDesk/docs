---
description: Create an assignment in the Jupyter Notebook format prepared for grading.
---

# Step 3: Create your First Assignment Source File

## Creating an Assignment

When you first log into the `Grader Console`, you will notice that there is an assignment already created for you if you added the [quickstart assignment from Step 1](create-a-quickstart-assignment.md), named `PS1`. This assignment is there to help you get started but you can add your own assignment files too. For the purposes of this getting started guide we will use the included `PS1` assignment.

The grader's first task is to validate the Jupyter Notebook file itself. Click on the `ps1` link in the `Name` column to open a new tab so you can view the contents of the file:

![Click onClick on the included ps1 file to view the file&apos;s contents. the included ps1 file to view the file&apos;s contents.](https://files.readme.io/2f6a8c4-Screen_Shot_2020-02-14_at_12.27.13_PM.png)

Clicking on the assignment name within the `Name` column will open a Jupyter Notebook within a new browser tab. To view the file, click on the `problem1.ipynb` file link. To make sure you are working on a source file, validate that it is located within the `{course_name}/source/ps1` path:

![Assignment file located within the source directory.file located within the source directory.](https://files.readme.io/6d748e4-Screen_Shot_2020-02-14_at_12.33.25_PM.png)

### Browser Tabs

{% hint style="info" %}
### Browser Tabs

At this point, you may be wondering why so many browser tabs are open. We are aware that this could lead to confusion and are working hard on providing you with a more seamless workflow. Stay tuned!
{% endhint %}

Now, let's surface the user interface elements that will allow us to update the Jupyter Notebook cell meta-data. Click on the `View --> Cell Toolbar --> Create Assignment` option:

![Display create assignment GUI elements](https://files.readme.io/42e47db-Screen_Shot_2020-02-14_at_12.46.35_PM.png)

Several cell types are supported, these include:

* **Manually graded answer**: this option identifies cells \(both markdown and code cells\) which should be manually graded. Manually graded cells will also display a points value so that graders can add the points to the answer during the grading process.
* **Manually graded task**: tasks are used when the instructor needs the student to add their answer with _additional_ cells instead of adding the answer within the cell itself.
* **Autograded Answer**: these cells are used to define the answers needed by the auto-grader service. The student's version should create the same output as the solution answer.
* **Autograder tests**: these are used to assign the points value after running the tests with the auto-grader service. Essentially these are unit tests to validate the output of the `Autograded Answer` outputs.
* **Read-only**: these cells are locked, i.e. not editable by learners.

`Manually graded tasks` and `Autograder task` values display `Points` and `ID`:

![Points and ID fields for autograded tests and manually graded tasks.](https://files.readme.io/b6e2d2d-Screen_Shot_2020-02-14_at_1.03.19_PM.png)

You are free to choose any points value \(as a number\). Also, you can use any value of the ID field, as long as it is unique. Once you have added points to all `Manually graded tasks` and `Autograder task` values a total points value will update in the main cell toolbar. This represents the total points for the Notebook.

## Customize Student Version with Special Syntax

The auto-grader service needs special syntax located within the assignment cells to customize the student version of the Jupyter Notebook. Use-cases include:

1. Hiding answers from students when releasing assignments
2. Adding answers for manually graded markdown cells
3. Allow students to test code with hidden tests

## Hide Answers

Solutions are equivalent to answers. Solutions are delimited by the `### BEGIN SOLUTION` and `### END SOLUTION` tags. Solution sources are hidden from students. Code located between the commented `### BEGIN SOLUTION` and `### END SOLUTION` region is replaced with:

```text
# YOUR CODE HERE
raise NotImplementedError
```

If the student doesn't add an answer, the auto-grader service will assign 0 points for the cell that contains the auto-graded test for the solution.

{% hint style="info" %}
### Code Comments

Make sure you use the correct code comments for the programming language in use by your Jupyter Notebook kernel. For example `###` for Python and `//` for Javascript. If you don't add comments for the solution region, then the auto-grader service will replace all cell contents with `YOUR ANSWER HERE`.
{% endhint %}

## Hiding Tests

You can hide some or all tests located within the `Autograder tests` cells. The region between the `BEGIN HIDDEN TESTS` and `END HIDDEN TESTS` allow will hide tests when the assignment is released.

Partially hidden tests are useful for when the teacher would like to provide the student with some tests to validate their answer but hide other tests that may offer a clue to how to structure the solution.

## Validate Assignment

The auto-grader includes a `Validate` button to validate the Notebook's format to make sure that all tests pass. You can, of course, run the cells in order and obtain the same level of validation, but the `Validate` button provides a one-click and only focuses on the `Autograded tests` that assert results located within the `Autograded answers`. This step will ensure that the auto-grader will not encounter unexpected errors and return inaccurate results when calculating grades.

The `Validate` button is located in the Jupyter Notebooks cell toolbar:

![The validate button helps validate the source notebook](https://files.readme.io/1607754-validate_assignment.png)

## Answers for Manually Graded Markdown Cells

The auto-grader service will hide answers located between the `=== BEGIN MARK SCHEME ===` and `=== END MARK SCHEME ===` region. This allows teachers to view answers during manual grading.

{% hint style="warning" %}
### Manual vs Auto Grader Syntax

You may have noted the use of the `===` for the mark scheme region above. Unlike the auto-graded answer and test regions, the manually graded regions _must_ include these three equal symbols before and after the mark scheme region.
{% endhint %}

The `Points` text box is available for cells defined as `Autograder tests` and `Manually graded tests`. The sum of these integers is located at the top of the Jupyter Notebook, within the cell toolbar:

{% hint style="info" %}
### One Assignment, Multiple Notebooks

One assignment may contain multiple Jupyter Notebook files. Nevertheless, these files may reference other files, such as CSV data sets within the same folder or as publicly available URLs.
{% endhint %}

## Create your Own Source File

Feel free to create your own version or update the file itself. Make sure to save your work before moving on to the next step, which is to release the assignment to your learners!

