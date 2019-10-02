Great! The build artifacts will now be uploaded to the artifact storage. If you wait for the workflow to finish, you'll notice the `test` job still fails. This is for a number of reasons:
- jobs run in parallel, unless configured otherwise 
- each job runs in its own virtual environment, so although we've pushed our artifacts to storage, the `test` job needs to retrieve them.

To remedy this, we'll run `test` only after `build` is finished so the artifacts are available, and we'll use another action built by GitHub, [`actions/download-artifact`](https://github.com/actions/download-artifact) to retrieve artifacts from the `build` job.

1. Edit your [workflow file]({{ fileUrl }})
1. Configure the `test` job to run only after the `build` job is completed (we'll use ellipses `...` to only show the parts of the workflow we're interested in, but you should not copy the ellipses directly):
    ```yaml
      test:
        needs: build
        runs-on: ubuntu-latest
        ...
    ```
1. Add a step to your `test` job that uses the `download-artifacts` action.
    ```yaml
      test:
        needs: build
        runs-on: ubuntu-latest
        ...
        steps:
        - uses: actions/checkout@v1
        - uses: actions/download-artifact@master
          with: 
            name: webpack artifacts
            path: public
        - name: Use Node.js ${{ matrix.node-version }}
          uses: actions/setup-node@v1
          with:
            node-version: ${{ matrix.node-version }}
        - name: npm install, and test
          run: |
            npm install
            npm test
          env:
            CI: true
    ```

I'll respond when you've edited your workflow file. 