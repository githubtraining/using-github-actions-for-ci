The `jobs:` block defines the core component of an Actions workflow. Workflows are made of jobs, and our template workflow defines a single job with the identifier `build`. 

Every job also needs a specific host machine on which to run, the `runs-on:` field is how we specify it. The template workflow is running the `build` job in the latest version of Ubuntu, a Linux-based operating system. 

To learn more about the fields discussed here, see:
- [Workflow syntax for GitHub Actions: `jobs:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobs) on GitHub Help 
- [Workflow syntax for GitHub Actions: `jobs.<job_id>:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_id) on GitHub Help 
- [Workflow syntax for GitHub Actions: `jobs.<job_id>.runs-on:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idruns-on) on GitHub Help 
- [Virtual environments for GitHub Actions](https://help.github.com/en/articles/virtual-environments-for-github-actions) on GitHub Help
- [Ubuntu](https://en.wikipedia.org/wiki/Ubuntu) on Wikipedia