# Automate your pipeline test
By doing this, you can make your pipeline robust, efficient and well tested. 
Here are some guidlines:

## Build an end to end Test to Whole pipeline
First focus on infra, provide input, do simple transformation and test with expected output. 

## Use small amount of data to test
To run your test, data will be small enough to finish pipeline withing few minutes. Always use production but anonymized data to test.

## Prefer textual data format over binary to test
Textual data format will help to understand what is happening and why the test fails. If the pipeline accept or produce only binary output, change it or do some transformation so that it can accept textual data format as well.

## Ensure the tests run on locally
It makes easy to dubug test failures. Minimize the use of cloud service and run the test under CI process too. 

## Make test determinstic
Sometimes the order of output records doesn’t matter in your application. For testing, however, you may want an extra step to sort by a field to make the output stable.

Avoid having variable time fields be a part of the output. This should be pos‐ sible by providing fixed input; otherwise, consider mocking out time, or post-processing the output to strip out time fields. If all else fails, match out‐ puts by a similarity measure rather than strict equality.

## Make It Easy to Add More Tests
Parameterize input file based so that same test can be run on multiple files. 