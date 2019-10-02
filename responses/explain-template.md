Great job adding the templated workflow. Simply adding that file to this branch is enough for GitHub Actions to begin running CI on your repository. This takes a couple of minutes, so let's take this opportunity to learn about some of the components of the workflow file you just added. We'll dive deeper into some of the key elements of this file in future steps of the course. 

I'll respond when GitHub Actions finishes running the workflow. You can follow along in the [Actions tab]({{ actionsUrl }}), or by clicking Details on the pending status below. 

---

<details><summary>Actions workflow not running? Click here</summary>

When a GitHub Actions workflow is running, you should see some checks in progress, like the screenshot below. 

![checks in progress in a merge box](https://user-images.githubusercontent.com/16547949/66080348-ecc5f580-e533-11e9-909e-c213b08790eb.png)

If the checks don't appear or if the checks are stuck in progress, there's a few things you can do to try and trigger them:

- Refresh the page, it's possible the workflow ran and the page just hasn't been updated with that change
- Try making a commit on this branch. Our workflow is triggered with a `push` event, and committing to this branch will result in a new `push`
- Edit the workflow file on GitHub and ensure there are no red lines indicating a syntax problem
</details>