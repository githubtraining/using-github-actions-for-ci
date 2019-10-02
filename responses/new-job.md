Great, if you look at the logs now, you'll notice that multiple builds will exist: 4 build to be exact! That's because for each of the 2 operating systems we're running tests against 2 versions so: 2 OS :heavy_multiplication_x: 2 Node.js versions = 4 builds.

Our custom workflow now accounts for:
- :white_check_mark: **test against multiple targets** so that we know if our supported operating systems and Node.js versions are working

Let's now try to create a dedicated test job. This will allow us to separate the build and test functions of our workflow. If you'd like to learn more about jobs, see:
- [About GitHub Actions: Job](https://help.github.com/en/articles/about-github-actions#job) in GitHub Help
- [About CI: Job](https://help.github.com/en/articles/about-continuous-integration#job) in GitHub Help
- [Workflow syntax for GitHub Actions: `jobs`](https://help.github.com/en/articles/workflow-syntax-for-github-actions#jobs) in GitHub Help

1. Edit [your workflow file]({{ fileUrl }})
1. Create a new job called "test" as follows (we'll use ellipses `...` to only show the parts of the workflow we're interested in, but you should not copy the ellipses directly):
  ```yaml
  name: Node CI

  on: [push]

  jobs:
    build:
      ...
    test:
      ...
  ```  
1. In the `build` job, include the following portions of your existing workflow:
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
1. In the newly created `test` job, include the following portions of your existing workflow:
  ```yaml
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        os: [ubuntu-lastest, windows-2016]
        node-version: [8.x, 10.x]
    steps:
    - uses: actions/checkout@v1
    - name: Use Node.js $\{{ matrix.node-version }}
      uses: actions/setup-node@v1
      with:
        node-version: $\{{ matrix.node-version }}
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

    needs: build

    runs-on: ubuntu-latest

    strategy:
      matrix:
        os: [ubuntu-lastest, windows-2016]
        node-version: [8.x, 10.x]

    steps:
    - uses: actions/checkout@v1
    - name: Use Node.js $\{\{ matrix.node-version }}
      uses: actions/setup-node@v1
      with:
        node-version: $\{\{ matrix.node-version }}
    - name: npm install, and test
      run: |
        npm install
        npm test
      env:
        CI: true
```
</details>

I'll respond when you commit to this branch.