## Step 5: Fix the test

This line is causing the problem. Let's fix it by initializing this instance of `p2` to the proper value. 

### :keyboard: Activity: Edit the file that's causing the test to fail

Edit the `src/game.js` file directly, or accept the suggestion below.

```suggestion
    this.p2 = p2
```

Once you commit the changes, the tests will run again and should pass. I'll respond when the tests pass. If the tests don't pass, I'll provide some troubleshooting information.