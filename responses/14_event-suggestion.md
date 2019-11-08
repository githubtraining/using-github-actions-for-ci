## Step 15: Use an action to automate pull request reviews

Trigger your review workflow. Apply the suggestion or follow the instructions to do it directly.

### :keyboard: Activity: Use the community action in your new workflow

```suggestion
name: Team awesome's approval workflow
on: pull_request_review
```

1. Edit your newly created [workflow file]({{ editUrl }})
1. Below the title, run the workflow on a pull request review event:
    ```yaml
    on: pull_request_review
    ```
1. Commit your changes to this branch

I'll respond when you commit something to this branch.