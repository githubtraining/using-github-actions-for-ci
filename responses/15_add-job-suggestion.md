## Step 16: Create an approval job in your new workflow

### :keyboard: Activity: In your new workflow file, create a new job that'll use the community action

1. Edit your newly created [workflow file]({{ editUrl }})
1. Create a new job called `labelWhenApproved`.
    ```suggestion
    on: pull_request_review
    jobs:
      labelWhenApproved:
        runs-on: ubuntu-latest
    ```
1. Commit your changes to this branch

I'll respond when you commit something to this branch.
