Remember our custom workflow? Here's where we are:

- [ ] branch protections
- [ ] required review approvals
- [ ] easy way to see when enough approvals has been achieved
- [x] matrix build
- [x] save build artifacts
- [x] dedicated test job

The last three remaining items don't really belong in a code build and test pipeline. So let's do these in a separate workflow file. 

1. Create a new file, `.github/workflows/approval-workflow.yaml`, on this branch
1. Enter a name for your workflow in the new file, something like:
    ```yaml
    name: Team awesome's approval workflow
    ```

I'll respond when you make thsee changes.