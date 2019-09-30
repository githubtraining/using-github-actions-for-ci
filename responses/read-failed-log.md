If you dig deeper into the logs, you may notice this error in particular:

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

This tells us that a unit test has been written that names the two players Salem and Nate, and then checks if that name sticks. However, we get :banana: Bananas instead of Nate! It's common practice to name test files the same as the code file they are testing, but with a `.test.js` extension. Therefore, we can assume that this error is caused by a problem in the `game.js` file. I'll point it out below.