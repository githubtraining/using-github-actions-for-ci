Awesome!

Let's talk about jobs a little here.

Let's add a new job so that we can separate the build and test steps. Commit a new job to your workflow file, call it "test".

```yaml
name: Node CI

on: [push]
jobs:
  build:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        os: [ubuntu-lastest, windows-2016]
        node-version: [8.x, 10.x]
    steps:
    - uses: actions/checkout@v1
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v1
      with:
        node-version: ${{ matrix.node-version }}
    - name: npm install
      run: |
        npm install
      env:
        CI: true
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        os: [ubuntu-lastest, windows-2016]
        node-version: [8.x, 10.x]
    steps:
    - uses: actions/checkout@v1
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v1
      with:
        node-version: ${{ matrix.node-version }}
    - name: npm test
      run: |
        npm test
      env:
        CI: true
```