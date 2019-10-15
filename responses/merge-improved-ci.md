Awesome work! Merge this pull request so our new CI workflow is available to the entire team. Our custom workflow now accounts for:
- :white_check_mark: **test against multiple targets** so that we know if our supported operating systems and Node.js versions are working
- :white_check_mark: **dedicated test job** so that we can separate out build from test details
- :white_check_mark: **access to build artifacts** so that we can deploy them to a target environment

In the next few steps, we'll finish supporting our team's workflow:
- **branch protections** so that the `master` branch can't be deleted or inadvertently broken
- **required reviews** so that any pull requests are double checked by teammates
- **obvious approvals** so we can merge quickly and potentially automate merges and deployments

I'll respond when you merge this pull request.