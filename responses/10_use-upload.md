The workflow has finished running!

You may notice `build` succeeded, but each of the `test` jobs failed. That's because the build artifacts created in `build` aren't available to the `test` job. Each job executes in a fresh instance of the virtual environment. This is due to the [design of the virtual environments](https://help.github.com/en/articles/virtual-environments-for-github-actions#about-virtual-environments) themselves.

So what do we do when we need the work product of one job in another? We can use the built-in [artifact storage](https://help.github.com/en/articles/persisting-workflow-data-using-artifacts).

### Using the artifact storage

First, we'll need to save the artifacts created from `build`. We can use an action built by GitHub to do this: [`actions/upload-artifacts`](https://github.com/actions/upload-artifact).

1. Edit [your workflow file]({{ fileUrl }})
1. Add a step to your `build` job that uses the `upload-artifacts` action.
    ```yaml
      build:
        runs-on: ubuntu-latest
        steps:
          - uses: actions/checkout@v1
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