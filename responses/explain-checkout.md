A job is made up of steps, and this section of the workflow file starts defining the `build` job's steps.

To properly run tests against our codebase, the virtual machine needs a copy of it. Therefore, the first step will be to use an action that performs a `git clone` of your repository within the virtual environment and performs a `git checkout` to a specified branch, commit, or tag. Our template just points to the latest commit on the master branch.


To learn more about the fields discussed here, see:
- [Workflow syntax for GitHub Actions: `jobs:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobs) on GitHub Help 
- [Workflow syntax for GitHub Actions: `jobs.<job_id>:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_id) on GitHub Help 
- [Workflow syntax for GitHub Actions: `jobs.<job_id>.runs-on:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idruns-on) on GitHub Help 
- [Virtual environments for GitHub Actions](https://help.github.com/en/articles/virtual-environments-for-github-actions) on GitHub Help