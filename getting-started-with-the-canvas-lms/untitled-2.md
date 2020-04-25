# Step 9: Grade Assignments and Release Feedback



### Automated Grading vs Manual Grading

As the name implies, the automated grading service automates grading tasks. This is a huge time saver, particularly for organizations that have large numbers of remote students. Manual grading consists of having a human review and grade assignment answers. Graders also have the option of adding comments to the Jupyter Notebook file so students have more insight on the accuracy of their answers.

### Collect Submitted Assignments

After all \(hopefully\) students have submitted their assignments, the grader needs to collect the assignments so that they can complete the grading tasks. At first, it will look like there are no submissions since the number of submissions is set to 0:

![Collect submitted assignments](https://files.readme.io/cdd5ff8-collect_submittted_assignments.png)

After clicking on the icon located in the `Collect` column, the `# Submissions` integer value should reflect the number of students submissions. Since we are only testing with one user, this value is `1`:

![Number of assignments submitted by learners](https://files.readme.io/60e59e3-collect_assignment_submissions_1.png)

### Auto-Grade Assignments

After collecting the assignments click on the integer value within the `# Submissions` column to view the submissions in a table, where the rows represent the student and the actions you can take for each student submission.

Notice how a badge appears with the `needs autograding` label, which indicates that the user should initiate the auto-grader job. To run the auto-grading job, simply click on the icon located within the `Autograde` column.

![Badge indicates that auto-grading job si pending.](https://files.readme.io/f2fa3ff-autograding_before_autograding.png)

Once the Auto-Grading service completes, a modal will appear letting you know that the grading task has completed successfully. Additionally, a new badge will appear under the `Status` column which should indicate that manual grading is pending. Also, notice that we have our first points assigned to the grade, which correspond to the automated grading cells only.

![Indicators which let the grader user know that there are manual grading tasks pending.](https://files.readme.io/1bdd137-Screen_Shot_2020-02-15_at_3.07.14_PM.png)

### Access Manual Grading Interface

To get started with manual grading, click on the link in the `Student Name` column. If the student does not have a first name or last name then the `None, None` values appear instead. Click on this link to open the learner's assignment items, which in this case are `Problem1` and `Problem2`.

In the example below, notice how a checkmark appears in the `Needs manual grade?` column. Also, the points value for each grading type are displayed:

* **Code score**: points related to code cells that were designated as auto-graded tests and answers
* **Written score**: related to cells that were designated as manually graded answer
* **Task score**: related to cells that were designated as a manually graded task

![Clicking on the student name will display the items that need manual grading.](https://files.readme.io/d35e511-needs_manual_grading.png)

Let's go ahead and start the **manual grading process** by clicking on one of the `Notebook ID` items. Actually, you can click on any of the `Notebook ID` items to open the manual grading interface. Then, within the manual grading interface, you can click on `Next` or `Previous` to access any of the `Notebook IDs` for the student's assignment.

![Manual grading view when viewing an individual Notebook ID](https://files.readme.io/68d0701-assignment_navigation_notebookid.png)

The manual grading interface is where graders can provide additional feedback, regardless of whether the cell was set up for manual or auto-grading!

### Manually Add Feedback and Confirm Points

Cells that were defined as `Automated Answers` when setting up the original source assignment are titled `Student's Answer`. **The grader may add comments to this cell**, even though the cell has already been graded by the auto-grader. This is also known as providing `Feedback`. \(In the next section, we will go over how to distribute this feedback back to the learners\):

{% hint style="warning" %}
#### Overriding Points Results

It is possible that the auto-grader completed all tasks successfully and that the service did not encounter or return any errors during the process, but rather, the tests to grade the student's solutions were not defined properly by the grader. These are the situations where it may make sense to override the calculated grade in the screenshot above.
{% endhint %}

![Cells defined with Automated answer are titled Student&apos;s answer](https://files.readme.io/ffb6449-student_answer_manual_grading.png)

Cells designated as `Automated test` have the cell id as the cell identifier and also have the points fields where the grader can adjust the points calculated by the auto-grader.

![Automated tests are displayed with the cell id and the points value assigned to the test after the grading process has completed.](https://files.readme.io/1acfa6e-autograding_tests_points_extra_credit.png)

Let's complete the grading process by adding some comments with markdown. Adding comments with markdown will help learners view the text in richer formats, such as lists and sections with headers. Also, you can click on the `Full credit` and the `No credit` buttons or full points or 0 points, respectively:

![Add comments and use the full credit / no credit buttons to quickly update points for each cell.](https://files.readme.io/94744a4-add_grader_comments.png)

Your comments and points values are automatically saved once you click on the `Next` button and have finished viewing the last `Notebook ID` within the assignment.

### Release Feedback to Your Learners

Before we move on to the next section, where we will collect feedback as students let's click on the icon located in the `Generate Feedback` column to send feedback to your students. Students can then collect feedback \(although they aren't forced to\) to enhance their understanding of the material.

![Generate and release feedback to learners.](https://files.readme.io/9901b49-generate_feedback.png)

Once feedback is released, a badge with the `released` label will appear in the `Status` column, as depicted in the image above.

Woot! You have completed your grading tasks and have submitted feedback to your learners. There are only two steps left!

1. Collect and view feedback as a learner
2. Send the assignment's grades to the Learning Management System \(LMS\)

