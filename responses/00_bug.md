# Welcome

In this repository, we'll be diving into the world of Continuous Integration. **Continuous Integration**, or **CI**, can benefit your projects and change how you work on GitHub. If you're new to Continuous Integration, you may be thinking, "What exactly is it, and do I need it in my project?"

### What is CI? Why should you care?

<p align="center">
  <img src="https://user-images.githubusercontent.com/6351798/88584678-3e81c400-d00f-11ea-95e0-01d8708c6e84.png">
</p>

[CI](https://en.wikipedia.org/wiki/Continuous_integration) can help you stick to your team’s quality standards by running tests and reporting the results on GitHub. CI tools run builds and tests, triggered by commits. The results post back to GitHub in the pull request. This reduces context switching for developers, and improves consistency for testing. The goal is fewer bugs in production and faster feedback while developing.

Choices around CI that will work best for your project depend on many factors, including:

- Programming language and application architecture
- Operating system and browsers you plan to support
- Your team’s experience and skills
- Scaling capabilities and plans for growth
- Geographic distribution of dependent systems and the people who use them
- Packaging and delivery goals

### Using CI and Learning Lab

In other courses, you may have noticed that some actions take me longer to respond to than others. In this course, many of the actions will be related to builds. Those builds sometimes take longer to build, up to several minutes. Don't be concerned if I take a few minutes to respond, or if I respond too quickly. Sometimes, I'll let you know what the build will say before it finishes! Please wait for the builds to finish before moving on to your next step.

If you aren't already familiar, it may be a good idea to go through the [Introduction to GitHub Learning Lab](https://lab.github.com/githubtraining/introduction-to-github).

## Step 1: Use a templated workflow

<img align="left" width="100" height="100" src="https://user-images.githubusercontent.com/6351798/88585528-6f162d80-d010-11ea-8efa-1e6d6d8bcb99.png">

There's a bug somewhere in this repository. We'll use the practice of Continuous Integration (CI) to set up some automated testing to make it easier to discover, diagnose, and minimize scenarios like this.

Let's first introduce CI to this repository. The codebase is written with Node.js. GitHub Actions allows us to use some templated workflows for common languages and frameworks, like Node.js! Let's add it:

### :keyboard: Activity: Create a pull request with a templated workflow

1. Go to the [Actions tab]({{ actionsUrl }}).
2. Choose the template Node.js workflow.
3. Commit the workflow to a new branch.
4. Create a pull request titled **CI for Node**.

I'll respond in the new pull request when I detect it has been created.

---

If at any point you're expecting a response and don't see one, refresh the page.
