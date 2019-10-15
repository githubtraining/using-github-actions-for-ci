1. Edit your newly created [workflow file]({{ editUrl }})
1. Create a new job called `labelWhenApproved`.
    ```suggestion
    on: pull_request_review
    jobs:
      labelWhenApproved:
    ```
1. Commit your changes to this branch