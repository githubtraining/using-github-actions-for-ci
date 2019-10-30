# Partial workflow

Remember the [custom workflow]({{ workflowIssue }}) we are attempting to create for the team? Here's our status on the list of requirements we defined:

- :white_check_mark: **test against multiple targets** so that we know if our supported operating systems and Node.js versions are working
- :white_check_mark: **dedicated test job** so that we can separate out build from test details
- :white_check_mark: **access to build artifacts** so that we can deploy them to a target environment
- **branch protections** so that the `master` branch can't be deleted or inadvertently broken
- **required reviews** so that any pull requests are double checked by teammates
- **obvious approvals** so we can merge quickly and potentially automate merges and deployments

The last three remaining items don't really belong in a `code, build, and test` pipeline because they have to do with processes that involve humans.

## Step 14: Automate the review process

GitHub Actions can run multiple workflows for different event triggers. Let's create a new approval workflow that'll work together with our Node.js workflow.

### :keyboard: Activity: Add a new workflow file to automate the team's review process

1. Create a [new file]({{ fileUrl }}), `.github/workflows/approval-workflow.yml`, on this branch
1. Enter a name for your workflow in the new file, something like:
    ```yaml
    name: Team awesome's approval workflow
    ```

I'll respond when you commit to this branch.