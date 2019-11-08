### Step 17: Hint

1. Edit the [workflow file]({{ editUrl }}) on this branch.
1. Give your step a name, have it use `pullreminders/label-when-approved-action@master`, and set all the required environment variables.
    ```suggestion
        runs-on: ubuntu-latest
        steps:
        - name: Label when approved
          uses: pullreminders/label-when-approved-action@master
          env:
            APPROVALS: "1"
            GITHUB_TOKEN: {% raw %}${{ secrets.GITHUB_TOKEN }}{% endraw %}
            ADD_LABEL: "approved"
    ```
1. Commit your changes to this branch. 