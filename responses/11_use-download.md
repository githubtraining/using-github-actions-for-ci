# Use the download

Great! The build artifacts will now be uploaded to the artifact storage. If you wait for the workflow to finish, you'll notice the `test` job still fails. This is for a number of reasons:
- jobs run in parallel, unless configured otherwise 
- each job runs in its own virtual environment, so although we've pushed our artifacts to storage, the `test` job needs to retrieve them.

## Step 12: Download a job's build artifacts

<img alt="icon of a binary file" align="left" width="100" height="100" src="https://user-images.githubusercontent.com/6351798/88592731-b2c26480-d01b-11ea-850e-c87588aadf4f.png">

To remedy this, we'll run `test` only after `build` is finished so the artifacts are available. 

Similar to the upload action to send artifacts to the storage, we'll use another action built by GitHub to download these previously uploaded artifacts from the `build` job: [`actions/download-artifact`](https://github.com/actions/download-artifact).

### :keyboard: Activity: Use the download action in your workflow file to access a prior job's build artifacts

_You can follow the manual steps below, or accept the suggestions in the following comments._

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
        - uses: actions/checkout@v2
        - uses: actions/download-artifact@main
          with: 
            name: webpack artifacts
            path: public
        - name: Use Node.js {% raw %}${{ matrix.node-version }}{% endraw %}
          uses: actions/setup-node@v1
          with:
            node-version: {% raw %}${{ matrix.node-version }}{% endraw %}
        - name: npm install, and test
          run: |
            npm install
            npm test
          env:
            CI: true
    ```
    
I'll respond when you've edited your workflow file. 
