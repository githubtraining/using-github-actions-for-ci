Let's add a job to your brand new workflow. 

```yaml
on: pull_request_review
name: Label approved pull requests
jobs:
  labelWhenApproved:
    name: Label when approved
    runs-on: ubuntu-latest
```

Remember that virtual environment? We'll talk a little about the `runs-on` here.