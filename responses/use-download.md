Great!

That uploads your artifacts, but the `test` job needs to be able to use them. There's another action, [`actions/download-artifact`](https://github.com/actions/download-artifact), that'll allow us to do just that. 

Add the following to your workflow file in the `test` job. 

```yaml
  test:
    needs: build
    runs-on: ubuntu-latest
    strategy:
      matrix:
        os: [ubuntu-lastest, windows-2016]
        node-version: [8.x, 10.x]
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