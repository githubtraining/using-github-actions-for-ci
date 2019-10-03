Great job creating a new workflow!

As we briefly discussed earlier, workflows can be configured to run:
- using events from GitHub,
- at a scheduled time, or
- when an event outside of GitHub occurs

Full details are available in [Events that trigger workflows](https://help.github.com/en/articles/events-that-trigger-workflows) on GitHub Help. So far, we've used the [`push` event](https://help.github.com/en/articles/events-that-trigger-workflows#push-event-push) for our Node.js workflow. That makes sense when we want to take action on code changes to our repository.

For a review workflow, we want to engage with human reviews, instead. For example, we'll use the [Label approved pull requests action](https://github.com/pullreminders/label-when-approved-action) so that we can easily see when we've gotten enough reviews to merge a pull request. 

Let's prep our review workflow by triggering it with a [`pull_request_review` event](https://help.github.com/en/articles/events-that-trigger-workflows#pull-request-review-event-pull_request_review)