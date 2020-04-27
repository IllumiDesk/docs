# Step 7: Submit Assignment for Grading

### Open Fetched Assignment

As a learner, open the fetched assignment to start working on completing all solutions:

![Open fetched assignment by clicking on the assignment file link](https://files.readme.io/3938066-open_fetched_assignment_as_student.png)

Clicking on the assignment file will open a Jupyter Notebook server in a new tab so the student \(learner\) can add all their answers. Like the grader, the student also has access to the validate button located within the Notebook's cell toolbar. The validate button is located within the learner's `Assignment` tab \(as illustrated above\) but also in the learner's Jupyter Notebook file.

To speed things up a bit copy/paste the answers below for the auto-graded cells. For the manually graded cells, any text will do.

**Problem 1 - Part A**Python

```text
def squares(n):
    """Compute the squares of numbers from 1 to n, such that the 
    ith element of the returned list equals i^2.
    
    """
    if n < 1:
        raise ValueError("n must be greater than or equal to 1")
    return [i ** 2 for i in range(1, n + 1)]
```

**Problem 1 - Part B**Python

```text
def sum_of_squares(n):
    """Compute the sum of the squares of numbers from 1 to n."""
    return sum(squares(n))
```

**Problem 1 - Part D**Python

```text
def pyramidal_number(n):
    """Returns the n^th pyramidal number"""
    return sum_of_squares(n)
```

`Problem 2` only has manually graded cells. Once you have added all the answers to your notebook files prepare for the submission step by saving your files and validating your answers with the `Validate` button mentioned above.

If the validation steps resulted in an error, it should display a modal with some information as to whay the validation step failed.

![Assignment validation error](https://files.readme.io/f94787c-validation_results.png)

#### Validation by Running All Cells

{% hint style="warning" %}
You can also validate the assignment file by running all cells. However, the validate button adds a more summarized view of where the failure occurred and why it occurred to give the learner more context. Running all cells will simply return the stack trace as cell output within the Jupyter Notebook file and those results are not available from within the Assignment tab.
{% endhint %}

You don't have to validate the assignment before submitting it, but its recommended, just in case you missed something :-\). Once your assignment is validated submit the assignment with the `Submit` button. Users have the option of **submitting assignments multiple times**. If this is the case, instructors which fetch the assignments pull the latest submission from the list.

![Multiple submissions from learners with the student role.](https://files.readme.io/366324c-submit_assignment_multiple_timestamps.png)

Whew! We've accomplished a lot so far and we are getting close to finishing the full grading process. In the next step, we will collect submitted assignments from students and grade them \(both automatically and manually\), provide feedback and release the feedback back to the students.  


