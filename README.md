# OctopusHTMLTestReport
Python OctopusHTMLTestReport uses the extent report template to generate reports

## Use
Based on the transformation of OctopusHTMLTestResult,OctopusHTMLTestCase the content of the page template of Extent report is used and methods of OctopusHTMLTestReport.

### How to initiate the test add details and status
Please follow the example bellow to use the Reporter Calss to open a file and add test cases details.

Also you can find the bellow code in the file example_test_run.py . just run it and report will be generated.

```
#!/usr/bin/env python3

from OctopusHTMLReport.OctopusReporter import Reporter

if __name__ == "__main__":
    # define opbect from the reporter calss to manage create the report file and add test cases details
    reporterX = Reporter()
    
    # initialize the reporting file by passing report path and project name
    reporterX.initReport("report.html","Octopus")

    # Test Case Reporting: use the methods passed, failed, info and error.
    
    #1. starting a test case node in the report
    reporterX.startTest("ValidateOctopusReport")
   
    #2. adding step details in the report for the opened test case
    reporterX.info("information log step1")
    reporterX.info("information log step2")
    reporterX.passed("information log passed")
    
    #3. closing the test case node details
    reporterX.stopTest()

    # repeat (1:3) for another 2 test cases with defferent status.
    reporterX.startTest("ValidateOctopusReport")
    reporterX.info("information log step3")
    reporterX.info("information log step4")
    reporterX.failed("information log failed")
    reporterX.stopTest()


    reporterX.startTest("ValidateOctopusReport")
    reporterX.info("information log step5")
    reporterX.info("information log step6")
    reporterX.error("information log error")
    reporterX.stopTest()

    # write the file details to the results folder.
    reporterX.writeReport()

```
