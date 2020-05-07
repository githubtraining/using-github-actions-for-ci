# New Job

Great, if you look at the logs now, you'll notice that multiple builds will exist: 4 build to be exact! That's because for each of the 2 operating systems we're running tests against 2 versions so: 2 OS :heavy_multiplication_x: 2 Node.js versions = 4 builds.

Our custom workflow now accounts for:
- :white_check_mark: **test against multiple targets** so that we know if our supported operating systems and Node.js versions are working

## Step 9: Use multiple jobs

Let's now try to create a dedicated test job. This will allow us to separate the build and test functions of our workflow.

### Activity: Edit your workflow file to separate build and test jobs

1. Edit [your workflow file]({{ fileUrl }})
2. Create a new job called "test" as follows (we'll use ellipses `...` to only show the parts of the workflow we're interested in, but you should not copy the ellipses directly):
    ```yaml
    name: Node CI

    on: [push]

    jobs:
      build:
        ...
      test:
        ...
    ```  
3. In the `build` job, include the following portions of your existing workflow:
    ```yaml
    build:
      runs-on: ubuntu-latest
      steps:
        - uses: actions/checkout@v1
        - name: npm install and build webpack
          run: |
            npm install
            npm run build
    ```
4. In the newly created `test` job, include the following portions of your existing workflow:
    ```yaml
    test:
      runs-on: ubuntu-latest
      strategy:
        matrix:
          os: [ubuntu-latest, windows-2016]
          node-version: [8.x, 10.x]
      steps:
      - uses: actions/checkout@v1
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

<details><summary>If you'd like to copy and paste the full workflow file instead, click here to see it in its entirety.</summary>

```yaml
name: Node CI

on: [push]

jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v1
      - name: npm install and build webpack
        run: |
          npm install
          npm run build

  test:

    runs-on: ubuntu-latest

    strategy:
      matrix:
        os: [ubuntu-latest, windows-2016]
        node-version: [8.x, 10.x]

    steps:
    - uses: actions/checkout@v1
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
</details>

When you commit to this branch, the workflow should run again. I'll respond when it is finished running.

---

<details><summary>Actions workflow not running? Click here</summary>

When a GitHub Actions workflow is running, you should see some checks in progress, like the screenshot below. 

![checks in progress in a merge box](https://user-images.githubusercontent.com/16547949/66080348-ecc5f580-e533-11e9-909e-c213b08790eb.png)

If the checks don't appear or if the checks are stuck in progress, there's a few things you can do to try and trigger them:

- Refresh the page, it's possible the workflow ran and the page just hasn't been updated with that change
- Try making a commit on this branch. Our workflow is triggered with a `push` event, and committing to this branch will result in a new `push`
- Edit the workflow file on GitHub and ensure there are no red lines indicating a syntax problem
</details>
