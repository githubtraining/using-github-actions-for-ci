## Vocabulary

#### Workflows, steps, actions, and jobs

![workflow](https://user-images.githubusercontent.com/6351798/88589835-f5ce0900-d016-11ea-8c8a-0e7d7907c713.png)

Let's dig into the vocabulary of GitHub Actions.

- **Workflow**: A workflow is a unit of automation from start to finish, including the definition of what triggers the automation, what environment or other aspects should be taken account during the automation, and what should happen as a result of the trigger.
- **Job**: A job is a section of the workflow, and is made up of one or more steps. In this section of our workflow, the template defines the steps that make up the `build` job.
- **Step**: A step represents one _effect_ of the automation. A step could be defined as a GitHub Action, or another unit, like printing something to the console.
- **Action**: A GitHub Action is a piece of automation written in a way that is compatible with workflows. Actions can be written by GitHub, by the open source community, or you can write them yourself!

#### What is `checkout`?

The power of **GitHub** Actions lies in access to actions written by the :sparkles: GitHub community. Here, we'll use two Actions officially written and supported by GitHub:
- `actions/checkout@v2` is used to ensure our virtual machine has a copy of our codebase. The checked out code will be used to run tests against.
- `actions/setup-node@v1` is used to set up proper versions of Node.js since we'll be performing testing against multiple versions.

To learn more about the fields discussed here, see:
- [Workflow syntax for GitHub Actions: `jobs.<job_id>.steps:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idsteps) on GitHub Help 
- [Referencing actions in your workflow](https://help.github.com/en/articles/configuring-a-workflow#referencing-actions-in-your-workflow) on GitHub Help
- Source repository for the [`actions/checkout`](https://github.com/actions/checkout) action
- Source repository for the [`actions/setup-node`](https://github.com/actions/setup-node) action
