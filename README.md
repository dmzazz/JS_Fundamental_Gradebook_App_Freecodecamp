# JS_Fundamental_Gradebook_App_Freecodecamp

# 🎓 Grading System - FreeCodeCamp Exercise Solution

This project contains the solutions to a step-by-step JavaScript exercise provided by [FreeCodeCamp](https://www.freecodecamp.org/learn/javascript-algorithms-and-data-structures-v8/review-js-fundamentals-by-building-a-gradebook-app/). The task is to help a teacher calculate average test scores, convert scores to letter grades, determine if students pass, and return a complete message for each student.

---

## 📘 Table of Contents

* [Step 1: Get Average](#step-1-get-average)
* [Step 2: Get Grade](#step-2-get-grade)
* [Step 3: Check Passing Grade](#step-3-check-passing-grade)
* [Step 4: Create Student Message](#step-4-create-student-message)
* [✅ Full Code](#️full-code)

---

## ✅ Step 1: Get Average

**Task:**
A teacher has finished grading their students' tests and needs your help to calculate the average score for the class.

Complete the getAverage function which takes in an array of test scores and returns the average score.

The average is calculated by adding up all the scores and dividing by the total number of scores.

average = sum of all scores / total number of scores A couple of function calls have been provided for you so you can test out your code.

**Tips:**
- You can use a loop to iterate over the scores array and add up all the scores. 
- You can use the length property to get the total number of scores.

**Solution:**

```js
function getAverage(scores) {
  let avg = 0;
  for(let i = 0; i < scores.length; i++){
    avg += scores[i] / scores.length
  }
  return avg;
}
```

**Example:**

```js
console.log(getAverage([92, 88, 12, 77, 57, 100, 67, 38, 97, 89]));
console.log(getAverage([45, 87, 98, 100, 86, 94, 67, 88, 94, 95]));
```

---

## ✅ Step 2: Get Grade

**Task:**
Now the teacher needs your help converting the student score to a letter grade.

Complete the getGrade function that takes a number score as a parameter. Your function should return a string representing a letter grade based on the score.

Here are the scores and their corresponding letter grades:

| Score Range | Grade |
| ----------- | ----- |
| 100         | A++   |
| 90–99       | A     |
| 80–89       | B     |
| 70–79       | C     |
| 60–69       | D     |
| 0–59        | F     |

**Tips:**
- Remember that you learned about conditional statements(if, else if, and else).
- Remember that you learned about comparison operators (>, <, >=, <=, ===).

**Solution:**

```js
function getGrade(score) {
  let grade = "";
  if (score == 100){
    grade = "A++"
  } else if (score >= 90 && score <= 99) {
    grade = "A"
  } else if (score >= 80 && score <= 89) {
    grade = "B";
  } else if (score >= 70 && score <= 79) {
    grade = "C";
  } else if (score >= 60 && score <= 69) {
    grade = "D";
  } else  {
    grade = "F"
  }
  
  return grade;
}
```

**Example:**

```js
console.log(getGrade(96));
console.log(getGrade(82));
console.log(getGrade(56));
```

---

## ✅ Step 3: Check Passing Grade

**Task:**
The teacher is really happy with the program you have created so far. But now they want to have an easy way to check if a student has a passing grade. A passing grade is anything that is not an "F".

Complete the function hasPassingGrade that takes a student score as a parameter. Your function should return true if the student has a passing grade and false if they do not.


**Tips:**
Use the getGrade function to get the student's grade. Then check if the grade is passing or not.Step 3 Solution

**Solution:**

```js
function hasPassingGrade(score) {
  return score >= 59;
}
```

**Example:**

```js
console.log(hasPassingGrade(100));
console.log(hasPassingGrade(53));
console.log(hasPassingGrade(87));
```

---

## ✅ Step 4: Create Student Message

**Task:**
Now that the teacher has all of the information they need, they want to be able to message the student with the results.

Complete the studentMsg function with totalScores and studentScore for parameters. The function should return a string representing a message to the student.

If the student passed the course, the string should follow this format:

```
Class average: 85.7. Your grade: B. You passed the course.
```

or

```
Class average: 74.5. Your grade: F. You failed the course.
```

**Tips:**
- Use the getAverage function to get the class average.
- Use the getGrade function to get the student's grade.
- Use string concatenation (+) to build the message.
- Be careful with the punctuation and spaces in the message.

**Solution:**

```js
function studentMsg(totalScores, studentScore) {
  const average = getAverage(totalScores);
  const studentGrade = getGrade(studentScore);
  const passed = hasPassingGrade(studentScore);
  return `Class average: ${average}. Your grade: ${studentGrade}. ${
    passed ? "You passed the course." : "You failed the course."
  }`;
}
```

---

## 🧹 Full Code

```js
function getAverage(scores) {
  let avg = 0;
  for(let i = 0; i < scores.length; i++){
    avg += scores[i] / scores.length
  }
  return avg;
}

function getGrade(score) {
  let grade = "";
  if (score == 100){
    grade = "A++"
  } else if (score >= 90 && score <= 99) {
    grade = "A"
  } else if (score >= 80 && score <= 89) {
    grade = "B";
  } else if (score >= 70 && score <= 79) {
    grade = "C";
  } else if (score >= 60 && score <= 69) {
    grade = "D";
  } else  {
    grade = "F"
  }
  
  return grade;
}

function hasPassingGrade(score) {
  return score >= 59;
}

function studentMsg(totalScores, studentScore) {
  const average = getAverage(totalScores);
  const studentGrade = getGrade(studentScore);
  const passed = hasPassingGrade(studentScore);
  return `Class average: ${average}. Your grade: ${studentGrade}. ${
    passed ? "You passed the course." : "You failed the course."
  }`;
}
```
