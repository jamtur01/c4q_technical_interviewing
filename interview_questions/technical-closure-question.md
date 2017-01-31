# Technical Interview

What is the expected output of the following example:

  ```
  var globalVar = "xyz";

  (function outerFunc(outerArg) {
    var outerVar = 'a';

    (function innerFunc(innerArg) {
      var innerVar = 'b';

      console.log(
        "outerArg = " + outerArg + "\n" +
        "innerArg = " + innerArg + "\n" +
        "outerVar = " + outerVar + "\n" +
        "innerVar = " + innerVar + "\n" +
        "globalVar = " + globalVar);

    })(456);
  })(123);
  ```
