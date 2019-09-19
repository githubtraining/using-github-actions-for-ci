Great!

That uploads your artifacts, but the `test` job needs to be able to use them. There's another action, [`actions/download-artifact`](https://github.com/actions/download-artifact), that'll allow us to do just that. 

Add the following to your workflow file in the `test` job. 

```yaml
- uses: actions/download-artifact@master
```

I'll respond when you've edited your workflow file. 