# GTestSetupUsingExternalProject  

## Running the tests  
### Using CLion IDE
- To run the all the tests inside `MyClassTest` you can use the run button at the test fixture or test name  
  - You can also right click a folder with tests and run all the tests or you can run individual tests using the green run button  
  - You can also run tests from the bottom pane that opens up after runnign tests initially  
   -  ![Run Tests using IDE](https://camo.githubusercontent.com/f909220c3da451214c25555afed0b12dcf538f667ec6aba16661e0164ffe6046/68747470733a2f2f692e6962622e636f2f384d386d46434e2f53637265656e73686f742d66726f6d2d323032312d30312d32352d32332d33342d30362e706e67)
   -  ![Run Tests using IDE](https://i.ibb.co/X2TLqRw/Screenshot-from-2021-01-26-01-15-28.png)
  - Using the IDE to run tests might provide better feedback than other alternatives (subjective)  
      
### Using CTest  
- go into `/build` and run `make && make test`, this will recompile your poject and run all the tests using CTest and give you a command-line print of the result.
  -  ![Run Tests using IDE](https://i.ibb.co/XjWWgxY/Screenshot-from-2021-01-26-01-17-25.png)
  
## Known issues and workaround  
### Global fixes to try :
- Delete `/build` folder and recreate/populate it using `mkdir build` + `cmake ..` + `make`  
- CLion : File->Invalidate cache & restart
#### Cannot run tests using play button :
- Try to right click your test class from the file explorer (inside CLion) and click "Run all in YourClassTest.cpp"  
- If it doesn't work try running your tests using `make test` from `/build` folder
#### Cannot find "gtest/gtest.h" / Don't have play button to run test inside my test class  :
- Try deleting `/build` and recreating/populating it using steps describe in _Global fixes to try_  
#### Code change is not reflected (test should fail but passes etc) : 
- Try re-running the test, maybe it was ran with outdated code or try `make && make test` from `/build`  
#### Could not build /cmake-build-debug does not exist :  
- Try File->Invalidate cache & restart
