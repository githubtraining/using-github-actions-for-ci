Now that we've learned how to quickly set up CI, let's try a more realistic use case!

Our fictional team has a custom workflow that goes beyond the template we've used so far. We would like the following features:
- **branch protections** so that we the `master` branch can't be deleted or inadvertently broken
- **required reviews** so that any pull requests are double checked by teammates
- **obvious approvals** so we can merge quickly and potentially automate merges and deployments
- **test against multiple targets** so that we know if our supported operating systems and Node.js versions are working
- **access to build artifacts** so that we can deploy them to a target environment
- **dedicated test job** so that we can separate out build from test details

Can GitHub Actions support this workflow? Let's find out. We'll tackle some of the changes to the existing workflow file first. 

Please:
1. Edit your [existing workflow]({{ workflowUrl }}) file in a new branch
1. In that file, target versions `8.x` and `10.x` of Node, only.
1. Open a new pull request titled **Improve CI** for your change.

I'll respond when you open the pull request.