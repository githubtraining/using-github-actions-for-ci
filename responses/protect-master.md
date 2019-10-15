Awesome! We can now check an additional requirement off our list!

- :white_check_mark: **test against multiple targets** so that we know if our supported operating systems and Node.js versions are working
- :white_check_mark: **dedicated test job** so that we can separate out build from test details
- :white_check_mark: **access to build artifacts** so that we can deploy them to a target environment
- :white_check_mark: **obvious approvals** so we can merge quickly and potentially automate merges and deployments
- **branch protections** so that the `master` branch can't be deleted or inadvertently broken
- **required reviews** so that any pull requests are double checked by teammates

We'll now use branch protections in combination with this change so that everything goes smoothly. Up until now, I've handled branch protections for you, but I've removed them so that you can learn how to set them. 

Take a look at the merge box, you'll notice you can merge this even though the review process hasn't been met. Still see the protection? Refresh this page. 

To add branch protections and continue with the course:
1. Go to [**Branches**]({{ settingsUrl}}/branches) settings. You can navigate to that page manually by clicking on the right-most tab in the top of the repository called **Settings** and then clicking on **Branches**.
1. Click on [**Add rule**]({{ settingsUrl }}/branch_protection_rules/new).
1. Type `master` in **Branch name pattern**.
1. Check **Require pull request reviews before merging**.
1. Check **Require status checks to pass before merging**. 
1. Check all build and test jobs that you'd like to see in the newly visible gray box.  
1. Click **Create**.
1. Return to this pull request, and approve the requested review.

I'll respond when I receive an approval from your pull request review. 