We've now got a job with the `labelWhenApproved` identifier. We're off to a great start!

It's now time to use a community-created action. The action we'll use is [pullreminders/label-when-approved-action](https://github.com/pullreminders/label-when-approved-action). Let's see if you can use this action on your own. If you'd like a hint, submit a comment on this pull request with the word "hint". 

Here's some tips to get you going:
- the workflow file needs a `steps:` block
- give your new step any name you wish
- to use a community action, use the `uses:` keyword
- `label-when-approved-action` requires a block called `env:` with the following environment variables:
  - `APPROVALS` is the number of required approvals that are required for a label to be applied, please set this to `"1"`
  - `GITHUB_TOKEN` is necessary so the action can create and apply labels to this repository. See the action's documentation for how to use it
  - `ADD_LABEL` is the name of the label which should be added when the number of approvals have been met, choose any label name you wish

I'll respond when you push a new commit to this branch.