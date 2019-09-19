Oh no your job failed! That's because the build artifacts created in the `build` job aren't available to the `test` job. Let's fix that.

First, we'll need to save the artifacts created from `build`. Use [`actions/upload-artifacts`](https://github.com/actions/upload-artifact) to upload to the build-in Actions artifact storage. 

I'll respond when you add the following line to your workflow file:
```yaml
- uses: actions/upload-artifact@master
```