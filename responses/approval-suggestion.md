Apply the suggestion or follow these instructions:
1. Edit your [approval workflow]({{ editUrl }}). 
1. Add a new job titled `labelWhenApproved`:
    ```yaml
    on: pull_request_review
    name: Label approved pull requests
    jobs:
      labelWhenApproved
    ```
1. Give your new job a name
    ```yaml
    ...
    jobs:
      labelWhenApproved:
        name: Label when approved
    ```
1. Configure your job to run on the `ubuntu-latest` virtual environment
    ```yaml
    ...
      labelWhenApproved:
        name: Label when approved
        runs-on: ubuntu-latest
    ```

```suggestion
on: pull_request_review
name: Label approved pull requests
jobs:
  labelWhenApproved:
    name: Label when approved
    runs-on: ubuntu-latest
```

