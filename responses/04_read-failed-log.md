One of the failing tests is: `Initializes with two players`. If you dig deeper into the logs, you may notice these results in particular:

```shell
  ● Game › Game › Initializes with two players

    expect(received).toBe(expected) // Object.is equality

    Expected: "Nate"
    Received: "Bananas"

      12 |     it('Initializes with two players', async () => {
      13 |       expect(game.p1).toBe('Salem')
    > 14 |       expect(game.p2).toBe('Nate')
         |                       ^
      15 |     })
      16 | 
      17 |     it('Initializes with an empty board', async () => {

      at Object.toBe (__test__/game.test.js:14:23)
```

This tells us that a unit test has been written that names the two players Salem and Nate, and then checks if that name sticks. However, we get :banana: Bananas instead of Nate! How did this happen?

To find out, it may help to know it's common practice to name test files the same as the code file they are testing, but with a `.test.js` extension. Therefore, we can assume that the test result from `game.test.js` is caused by a problem in `game.js`. I'll point it out below.

Make the changes suggested below. I'll respond when the workflow runs. 

---

<details><summary>Actions workflow not running? Click here</summary>

When a GitHub Actions workflow is running, you should see some checks in progress, like the screenshot below. 

![checks in progress in a merge box](https://user-images.githubusercontent.com/16547949/66080348-ecc5f580-e533-11e9-909e-c213b08790eb.png)

If the checks don't appear or if the checks are stuck in progress, there's a few things you can do to try and trigger them:

- Refresh the page, it's possible the workflow ran and the page just hasn't been updated with that change
- Try making a commit on this branch. Our workflow is triggered with a `push` event, and committing to this branch will result in a new `push`
- Edit the workflow file on GitHub and ensure there are no red lines indicating a syntax problem
</details>