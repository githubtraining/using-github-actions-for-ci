
## Step 8: Target a Windows environment

Since we'd like to support deploying our app to Windows environments, let's add Windows to the matrix build configuration. 

### :keyboard: Activity: Edit your workflow file to build for Windows environments

<img alt="an icon of three gears" align="left" width="100" height="100" src="https://user-images.githubusercontent.com/6351798/88591917-5ca0f180-d01a-11ea-8ed2-219aa3392cf2.png">

You can follow the suggestion, or manually make the changes in the numbered instructions.

```suggestion
        os: [ubuntu-latest, windows-2016]
        node-version: [8.x, 10.x]
```

1. Edit the workflow config at [`.github/workflows/nodejs.yml`]({{ fileUrl }})
2. Add an `os` field to the `strategy.matrix` section of your workflow
3. Add `ubuntu-latest` and `windows-2016` to the target operating systems
4. Commit your workflow changes to this branch.

I'll respond in this pull request when you've committed.
