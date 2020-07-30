# Use the upload

The workflow has finished running!

You may notice `build` succeeded, but each of the `test` jobs failed. That's because the build artifacts created in `build` aren't available to the `test` job. Each job executes in a fresh instance of the virtual environment. This is due to the [design of the virtual environments](https://help.github.com/en/articles/virtual-environments-for-github-actions#about-virtual-environments) themselves.

So what do we do when we need the work product of one job in another? We can use the built-in [artifact storage](https://help.github.com/en/articles/persisting-workflow-data-using-artifacts) to save artifacts created from one job to be used in another job within the same workflow. 

## Step 11: Upload a job's build artifacts

<img alt="icon of a binary file" align="left" width="100" height="100" src="https://user-images.githubusercontent.com/6351798/88592731-b2c26480-d01b-11ea-850e-c87588aadf4f.png">

Artifacts allow you to persist data after a job has completed, and share that data with another job in the same workflow. An artifact is a file or collection of files produced during a workflow run.

To upload artifacts to the artifact storage, we can use an action built by GitHub: [`actions/upload-artifacts`](https://github.com/actions/upload-artifact).

### :keyboard: Activity: Use the upload action in your workflow file to save a job's build artifacts

_You can follow the manual steps below, or accept the suggestion in the following comment._

1. Edit [your workflow file]({{ fileUrl }})
1. Add a step to your `build` job that uses the `upload-artifacts` action.
    ```yaml
      build:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v2
          - name: npm install and build webpack
            run: |
              npm install
              npm run build
          - uses: actions/upload-artifact@master
            with:
              name: webpack artifacts
              path: public/
    ```
1. Commit your change to this branch

I'll respond when you commit to this branch.
