# Running - and failing - workflow

The workflow ran! But it failed :sob:. But, that's OK. Every time CI fails, it's an opportunity to learn from what's causing it. By running CI with GitHub Actions, we have access to the logs for the attempted build. These are found:
- In the [Actions]({{ actionsUrl }}) tab
- In the merge box for this pull request, by clicking on "Details".

If you navigate over to the build logs, you may notice that the error is "No tests found".

![screenshot of build log showing a missing `__test__` directory](https://user-images.githubusercontent.com/16547949/65921324-eeff4700-e3af-11e9-8625-3aacfe64d06b.png)

Learning how to read build logs and isolate the cause of the problem is an art on its own. We'll try and cover some of the basics here. In our case, the source of the error is the `npm test` command. The `npm test` command looks for a testing framework. We want to use Jest, as we mentioned earlier. Jest requires unit tests in a [directory named `__test__`](https://jestjs.io/docs/en/configuration#testmatch-array-string). A `__test__` directory doesn't exist on this branch.

Not to worry, I've got you covered! Navigate to the open pull request titled [Add Jest tests]({{ url }}) and merge it into this branch. That'll get us the test files we need. I'll respond when you merge the [Add Jest tests pull request]({{ url }}) into this branch.
