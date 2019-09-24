It's now time to learn how to use and choose your own events to trigger workflows.

Later on, we'll use the [Label approved pull requests action](https://github.com/pullreminders/label-when-approved-action) so that we can easily see when we've gotten enough reviews to merge a pull request. In order to do this, we need to trigger the workflow for specific events. 

Add a trigger to your [new workflow]({{ editUrl }}):
```yaml
on: pull_request_review
```
