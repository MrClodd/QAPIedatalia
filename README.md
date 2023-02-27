# Tests QA API for Edatalia #

## 📫 <a name="section-installation">Getting Started</a>

### 💬 Previous Requirements

Required

- NodeJS 12
- Javascript

Recommended

- VS Code
- Postman

You should run this command:
```bash
  npm install
```
## 🚀 <a name="runJavaScriptFunction">To run JavaScript Function</a>

- Open the bash in the folder javaScriptFunction and run the following command.

```bash
  node functionMaxZeroBinary.js
```

## 📍<a name="usage">Usage</a>

### 📖 Run API test

```bash
  npm run test
```

## 💖 <a name="result">Result of Test Cases in Postman</a>

 The tests cases is ejecuting to check the API Rest on Edatalia
 
 <p align="center">
<img src="https://github.com/MrClodd/QAPIedatalia/blob/bbb3f84964de380299d4d37b5c447bd26a2f449c/2023-02-27%2014_04_12-Edatalia%20-%20My%20Workspace.png" width=90% height=90%>
 
<br>Test case 1: Max amount of 0s when the binary has multiple groups of 0s 
<br>Test Data: 545
<br>Binary is: 1000100001
<br>Result is: 4


<br>Test Case 2: Max amount of zeros when the binary has one group of 0s
<br>Test Data: 9
<br>Binary is: 1001
<br>Result is: 2

<br>Test Case 3: Max amount of zero when the binary only has 1s 
<br>Test Data: 7
<br>Binary is: 111
<br>Result is: 4

<br>Test Case 4: Max amount of zero when the binary has not group of 0s between 1s 
<br>Test Data: 16
<br>Binary is: 10000
<br>Result is: 4

<br>Test Case 5: Max amount of 0s when the binary has multiple groups of 0s 
<br>Test Data: 16666666666666666666666666 out of the range
<br>Result is: status 400
<br>Title of error: "One or more validation errors occurred.",
<br>Error number: "The value '16666666666666666666666666' is not valid."

## <a name="conclusion">Conclusion</a>

Validation on this collection just needs to insert some variables inside Postman and then check if the API returns the correct expected result according to the behavior mentioned at the beginning.
<br>The assertions can be seen for example: "pm.test("Status code is 200", function", helps us make sure that the behavior we are looking for tests the expected result. On the other hand, the test can be failed.

