Great! Here, we'll explain a little about matrix builds and how we target specific Node versions. We can also target specific OS's.

We'll be deploying our app to Windows environments. Let's add Windows to the matrix build configs.

Edit your NodeJS config so that we add Windows to the OS. Your build step should look like this:

```yaml
    strategy:
      matrix:
        os: [ubuntu-lastest, windows-2016]
        node-version: [8.x, 10.x]
```