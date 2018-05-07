# HTML Reporter
This script extension used to generate beautiful HTML reports by calling few functions. It creates HTML report for individual test case separately and High-level report which will have all the individual test cases and beautiful charts into it.

## Steps to use this Script Extension
1. Install script extension by using [this](https://support.smartbear.com/testcomplete/docs/working-with/extending/script/installing-and-uninstalling.html) link.

Sample script which you can try this SE.
```function testSEFlow(){
      HTMLUtilities.CompanyName = "TestComplete";
      HTMLUtilities.SetHTMLReportPath("C:\\SE-Report");
      HTMLUtilities.SetPlannedTestCaseCount(8);
      
      /*if you want to add server versions or AUT version you can add it here*/
      HTMLUtilities.SetAUTVersions("AUT-01-SYS","9.0");
      HTMLUtilities.SetAUTVersions("AUT-02-INT","9.1.0");
      
      
      HTMLUtilities.InitiateTestCase("test-case-01","this is test case description","test-env","test-module","bug-09787");
      HTMLUtilities.AddInformationToTestCase("This is just sample test cases");
      //if you want to add any files into the test case report you do like below
      aqFile.Create(HTMLUtilities.GetCurrentTestCasePath() + "sample-file.txt");
      HTMLUtilities.AddFileToTestCase("sample-file.txt","sampleFile");
      
      /*
       * 1 - Pass step
       * 2 - Warning step
       * 3 - Done step
       * 0 - Faile step
      */
      
      HTMLUtilities.LogStep(1,"Login validaiton","","",false,true);//put a header for a test steps
      HTMLUtilities.LogStep(1,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.CompleteTestCase();
      
      
      HTMLUtilities.InitiateTestCase("test-case-02","this is test case description","test-env","test-module","bug-09787");
      HTMLUtilities.LogStep(2,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.CompleteTestCase();
      
      
      HTMLUtilities.InitiateTestCase("test-case-03","this is test case description","test-env","test-module","bug-09787");
      HTMLUtilities.LogStep(0,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.CompleteTestCase();
      
      
      HTMLUtilities.InitiateTestCase("test-case-04","this is test case description","test-env","test-module","bug-09787");
      HTMLUtilities.LogStep(3,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.CompleteTestCase();
      
      
      HTMLUtilities.InitiateTestCase("test-case-05","this is test case description","test-env","test-module","bug-09787");
      HTMLUtilities.LogStep(1,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.LogStep(3,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.LogStep(1,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.LogStep(3,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.LogStep(1,"User should be able to login","User is able to login","Login page",false,false);
      HTMLUtilities.CompleteTestCase();
      HTMLUtilities.EndOfExecution(); 
}`


