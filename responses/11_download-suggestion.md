You can commit this suggestion directly.

```suggestion
    - uses: actions/download-artifact@master
      with:
        name: webpack artifacts
        path: public
    - name: npm install, and test
```