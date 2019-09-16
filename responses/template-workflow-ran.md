The template workflow ran! But it failed :(

That's because the template is looking for a test script (`npm test`). Let's add one. Edit the `package.json` file and add a test script as follows:

```json
  "test": "standard"
```

I'll respond when I detect you've committed. 