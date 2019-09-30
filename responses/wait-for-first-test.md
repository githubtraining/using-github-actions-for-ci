Great! Now that the testing framework is properly hooked up, we should get a response from it soon. This time, you'll practice reading the logs on your own. Just like before, you can follow along as GitHub Actions runs your job by going to the [Actions tab]({{ actionsUrl }}) or by clicking on "Details" in the merge box below. 

When the tests finish you'll see a red :x: or a green :heavy_check_mark: in the merge box. At that point, you'll have access to build logs our build job and the associated steps. 

By looking at the logs, can you identify which tests failed? You can find it by going to one of the failed builds, scrolling through the log, and looking for a section that lists all the unit tests. We're looking for the name of the test with an "x".

![screenshot of a sample build log with the names of the tests blurred out](https://user-images.githubusercontent.com/16547949/65922013-e740a200-e3b1-11e9-8151-faf52c30201e.png)

I'll respond when you enter the name of at least one failing test. You can either copy and paste that portion of the log directly, or enter the name of the test.