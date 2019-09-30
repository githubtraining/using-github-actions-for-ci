In addition to running pre-built actions, the workflow can also execute commands, just as you would if you had direct access to the virtual machine. In this portion of the template workflow, we run some common commands relevant to Node.js projects, like `npm install` to install dependencies and `npm test` to run the chosen testing framework.

To learn more about the fields discussed here, see:
- [Workflow syntax for GitHub Actions: `jobs.<job_id>.steps.run:`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobsjob_idstepsrun) on GitHub Help 
- [`npm install`](https://docs.npmjs.com/cli/install) on the npm Documentation 
- [`npm run`](https://docs.npmjs.com/cli/run-script) on the npm Documentation
- [`npm test`](https://docs.npmjs.com/cli/test.html) on the npm Documentation