A job is made up of steps, and this section of the workflow file starts defining the `build` job's steps.

To properly run tests against our codebase, the virtual machine needs a copy of it. Therefore, the first step will be to use an action that performs a `git clone` of your repository within the virtual environment and performs a `git checkout` to a specified branch, commit, or tag. We do this by using an Action built by GitHub. Our template just points to the latest commit on the master branch.


To learn more about the fields discussed here, see:
- [Workflow syntax for GitHub Actions: `jobs.<job_id>.steps:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idsteps) on GitHub Help 
- [Referencing actions in your workflow](https://help.github.com/en/articles/configuring-a-workflow#referencing-actions-in-your-workflow) on GitHub Help
- The [`actions/checkout`](https://github.com/actions/checkout) action