# Custom workflow

Now that we've learned how to quickly set up CI, let's try a more realistic use case.

Our fictional team has a custom workflow that goes beyond the template we've used so far. We would like the following features:

<img alt="an icon of three gears" align="left" width="50" height="50" src="https://user-images.githubusercontent.com/6351798/88609410-48241f80-d041-11ea-85ad-b77a5d08bfd1.png"><br/>
**Test against multiple targets** so that we know if our supported operating systems and Node.js versions are working

<img alt="icon of gears indicating relatiopnship between multiple jobs" align="left" width="50" height="50" src="https://user-images.githubusercontent.com/6351798/88609439-55410e80-d041-11ea-8186-09b2008e2572.png"><br/>
**Dedicated test job** so that we can separate out build from test details

<img alt="icon of a binary file" align="left" width="50" height="50" src="https://user-images.githubusercontent.com/6351798/88609455-5ffba380-d041-11ea-9e29-c2bac7a8dfd4.png"><br/>
**Access to build artifacts** so that we can deploy them to a target environment

<img alt="icon of a security shield indicating branch protections" align="left" width="50" height="50" src="https://user-images.githubusercontent.com/6351798/88609465-6a1da200-d041-11ea-9c4c-55ffe90a3e72.png"><br/>
**Branch protections** so that the `master` branch can't be deleted or inadvertently broken

<img alt="icon of a review approval" align="left" width="50" height="50" src="https://user-images.githubusercontent.com/6351798/88609558-9df8c780-d041-11ea-906f-dd23efd9f65c.png"><br/>
**Required reviews** so that any pull requests are double checked by teammates

<img alt="icon of a review approval" align="left" width="50" height="50" src="https://user-images.githubusercontent.com/6351798/88609481-73a70a00-d041-11ea-959d-27b33c2d4028.png"><br/>
**Obvious approvals** so we can merge quickly and potentially automate merges and deployments

## Step 7: Create a custom GitHub Actions workflow

Can GitHub Actions support this workflow? Let's find out. We'll tackle some of the changes to the existing workflow file first.

### :keyboard: Activity: Edit the existing workflow with new build targets

1. Edit your [existing workflow]({{ workflowUrl }}) file in a new branch
2. In that file, target versions `8.x` and `10.x` of Node, only
3. Open a new pull request titled **Improve CI** for your change.

I'll respond when you open the pull request.
