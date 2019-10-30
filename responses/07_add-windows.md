
```suggestion
        os: [ubuntu-lastest, windows-2016]
        node-version: [8.x, 10.x]
```

Since we'd like to support deploying our app to Windows environments, let's add Windows to the matrix build configuration. You can follow the suggestion above or manually make the changes as follows:
1. Edit the workflow config at [`.github/workflows/nodejs.yml`]({{ fileUrl }})
1. Add an `os` field to the `strategy.matrix` section of your workflow
1. Add `ubuntu-latest` and `windows-2016` to the target operating systems
1. Commit your workflow changes to this branch.

I'll respond in this pull request when you've committed.