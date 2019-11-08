# Waiting on tests

Great! We've now got two nicely separated `build` and `test` jobs. Our custom workflow now accounts for:
- :white_check_mark: **test against multiple targets** so that we know if our supported operating systems and Node.js versions are working
- :white_check_mark: **dedicated test job** so that we can separate out build from test details

If you'd like to learn more about jobs, see:
- [About GitHub Actions: Job](https://help.github.com/en/articles/about-github-actions#job) in GitHub Help
- [About CI: Job](https://help.github.com/en/articles/about-continuous-integration#job) in GitHub Help
- [Workflow syntax for GitHub Actions: `jobs`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobs)

## Step 10: Run multiple jobs

### :keyboard: Activity: Wait for the result of multiple jobs in your workflow

No action required in this step - just waiting. I'll respond when the workflow runs your jobs.

---

<details><summary>Actions workflow not running? Click here</summary>

When a GitHub Actions workflow is running, you should see some checks in progress, like the screenshot below. 

![checks in progress in a merge box](https://user-images.githubusercontent.com/16547949/66080348-ecc5f580-e533-11e9-909e-c213b08790eb.png)

If the checks don't appear or if the checks are stuck in progress, there's a few things you can do to try and trigger them:

- Refresh the page, it's possible the workflow ran and the page just hasn't been updated with that change
- Try making a commit on this branch. Our workflow is triggered with a `push` event, and committing to this branch will result in a new `push`
- Edit the workflow file on GitHub and ensure there are no red lines indicating a syntax problem
</details>