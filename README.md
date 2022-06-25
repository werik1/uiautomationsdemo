# UI Test Automation Framework 
UI test automation framework that utilizes Selenium WebDriver and TestNG.  This framework enables rapid test script creation with a selenium wrapper class that removes the need of writing low-level automation code.  It also generates a beautiful HTML-based test execution report after test executions.

***I would love to show you the framework in detail. Please contact me for a demo.***

## Project Dependencies
This projects depends on the following external libraries:
* **selenium-java**: browser automation code
* **webdrivermanager**: managing driver binaries through code
* **testng**: creating and managing test cases
* **extentreport**: generating HTML based test execution reports
* **javafaker**: generating randomized test data on the fly

## Pre-requisites
The execution environment must have the following tools installed locally
> * Download and install Chrome or Firefox browser
> * Download and install **[JDK v1.8+](https://www.oracle.com/java/techologies/downloads/)**
> * Download and install **[Apache Maven v3.0+](https://maven.apache.org/download.cgi)**
> * Download and install **[Git v2.0+](https://git-scm.com/downloads)**

## Framework Structures
#### Project Structures
```text
|- reports                # contains test report generated
|- src
    |- test
        |- java
            |- [+]base    # all the parent classes are organized here
            |- [+]pages   # all the page object class is organized here
            |- [+]tests   # all the test classes are organized here
            |- [+]util    # all the commonly used class is organized here
|- .gitignore             # add git ignore file config here
|- pom.xml                # maven project config file
```

#### Internal Structures
This is a diagram that details the internal structure of this framework.
![screenshot](/images/FrameworkStructure.jpg)

## How to Run Tests
All the test triggering is conducted by **`mvn`** commands. This framework supports test execution by multiple different browsers.

#### Supported Browsers:
| Browser         | Option String        |
|-----------------|----------------------|
| Chrome Headless | `-Dbrowser=headless` |
| Google Chrome   | `-Dbrowser=chrome`   |
| Mozilla Firefox | `-Dbrowser=firefox`  |
| Microsoft Edge  | `-Dbrowser=edge`     |

## Execution Triggers
This framework supports various test triggers. This is to make CI/CD integration much simpler as the test execution details can be configurable at the command line.

To trigger all text executions:
```shell
mvn test
```
To trigger specific tests:
```shell
mvn test -Dgroups=smoke
```
To trigger all or specific tests in a desired environment:
```shell
mvn test -Denv=staging
mvn test -Dgroups=smoke -Denv=staging
```
To trigger all or specific tests with a desired browser:
```shell
mvn test -Dbrowser=chrome
mvn test -Dgroups=smoke -Dbrowser=chrome
```
To trigger all or specific tests with a desired browser in a desired environment:
```shell
mvn test -Dbrowser=chrome -Denv=staging
mvn test -Dgroups=smoke -Dbrowser=chrome -Denv=staging
```

## How to view the report
All test execution reports are available as an HTML report in the 'reports' folder.
```test
|- reports
    |- Index.html
```
##### Sample Report:
Please navigate to this folder to view the test execution result. A sample ExtentReport will look like the following, with more test cases. [Reference](https://www.extentreports.com/docs/v5/wiki/spark/spark.html#)

![screenshot](/images/extentreportscreenshot.png)
