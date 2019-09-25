The template workflow ran! But it failed :(

That's because the template workflow calls `npm test`. That command is using Jest, and looks for a `__test__` folder with unit tests inside. That doesn't exist on this branch.

Not to worry, I've got you covered! Navigate over to the open PR titled [Add Jest tests]({{ url }}) and merge it into this branch. That'll get us the test files we need.

I'll respond when you merge the pull request into this branch. 