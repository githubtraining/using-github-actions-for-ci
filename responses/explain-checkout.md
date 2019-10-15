A job is made up of steps, and this section of the workflow, the template defines the steps that make up the `build` job.

The power of GitHub Actions lies in access to actions written by the :sparkles: GitHub community. Here, we'll use two Actions officially written and supported by GitHub:
- `actions/checkout@v1` is used to ensure our virtual machine has a copy of our codebase. The checked out code will be used to run tests against.
- `actions/setup-node@v1` is used to set up proper versions of Node.js since we'll be performing testing against multiple versions.

To learn more about the fields discussed here, see:
- [Workflow syntax for GitHub Actions: `jobs.<job_id>.steps:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idsteps) on GitHub Help 
- [Referencing actions in your workflow](https://help.github.com/en/articles/configuring-a-workflow#referencing-actions-in-your-workflow) on GitHub Help
- Source repository for the [`actions/checkout`](https://github.com/actions/checkout) action
- Source repository for the [`actions/setup-node`](https://github.com/actions/setup-node) action.