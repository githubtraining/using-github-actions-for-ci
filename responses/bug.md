Hello! 

There's a bug somewhere in this repository. We'll use the practice of Continuous Integration (CI) to set up some automated testing to make it easier to discover, diagnose, and minimize scenarios like this.

Let's first introduce CI to this repository. The codebase is written with Node.js. GitHub Actions allows us to use some templated workflows for common languages and frameworks, like Node.js! Let's add it:

1. Go to the [Actions tab]({{ actionsUrl }}).
1. Choose the template Node.js workflow.
1. Commit the workflow to a new branch.
1. Create a pull request titled **CI for Node**.

I'll respond in the new pull request when I detect it has been created.