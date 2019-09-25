Oh no your job failed! That's because the build artifacts created in the `build` job aren't available to the `test` job. Let's fix that.

First, we'll need to save the artifacts created from `build`. Use [`actions/upload-artifacts`](https://github.com/actions/upload-artifact) to upload to the build-in Actions artifact storage. 

I'll respond when you add the following line to your [workflow file]({{ fileUrl }}):
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