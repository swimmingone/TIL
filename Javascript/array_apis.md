# [Javascript] JS Array APIs 연습하기 (feat. 드림코딩 엘리)

드림코딩 채널의 JS 내장 배열 함수 영상의 문제 풀이를 정리해보았다.

[자바스크립트 9. 유용한 10가지 배열 함수들. Array APIs 총정리 | 프론트엔드 개발자 입문편 ( JavaScript ES6) - YouTube](https://youtu.be/3CUjtKJ7PJg)



---

## 문제

```js
// Q1. make a string out of an array
{
  const fruits = ['apple', 'banana', 'orange'];
}

// Q2. make an array out of a string
{
  const fruits = '🍎, 🥝, 🍌, 🍒';
}

// Q3. make this array look like this: [5, 4, 3, 2, 1]
{
  const array = [1, 2, 3, 4, 5];
}

// Q4. make new array without the first two elements
{
  const array = [1, 2, 3, 4, 5];
}

class Student {
  constructor(name, age, enrolled, score) {
    this.name = name;
    this.age = age;
    this.enrolled = enrolled;
    this.score = score;
  }
}
const students = [
  new Student('A', 29, true, 45),
  new Student('B', 28, false, 80),
  new Student('C', 30, true, 90),
  new Student('D', 40, false, 66),
  new Student('E', 18, true, 88),
];

// Q5. find a student with the score 90
{
}

// Q6. make an array of enrolled students
{
}

// Q7. make an array containing only the students' scores
// result should be: [45, 80, 90, 66, 88]
{
}

// Q8. check if there is a student with the score lower than 50
{
}

// Q9. compute students' average score
{
}

// Q10. make a string containing all the scores
// result should be: '45, 80, 90, 66, 88'
{
}

// Bonus! do Q10 sorted in ascending order
// result should be: '45, 66, 80, 88, 90'
{
}

```
---

## 풀이

```js
// Q1.
{
    const fruits = ['apple', 'banana', 'orange'];
    const result = fruits.join(',');
    console.log(result);
}


// Q2.
{
    const fruits ='apple, kiwi, banana, cherry';
    const result = fruits.split(',');
    console.log(result);
}

//Q3.
{
    const array = [1, 2, 3, 4, 5];
    const result = array.reverse();
    console.log(result);
    console.log(array); // both are reversed
}

//Q4.
{
    const array = [1, 2, 3, 4, 5];
    const result = array.slice(2, array.length); // splice vs slice
    console.log(result);
}

class Student {
    constructor(name, age, enrolled, score) {
        this.name = name;
        this.age = age;
        this.enrolled = enrolled;
        this.score = score;
    }
}
const students = [
    new Student('A', 29, true, 45),
    new Student('B', 28, false, 80),
    new Student('C', 30, true, 90),
    new Student('D', 40, false, 66),
    new Student('E', 18, true, 88)
];

//Q5.
{
    const result = students.find((student) => student.score === 90);
    console.log(result);
}
//Q6.
{
    const result = students.filter((student) => student.enrolled );
    console.log(result);
}

//Q7.
{
    const result = students.map((student) => student.score);
    console.log(result);
}

//Q8. 
{
    const result = students.some((student) => student.score < 50); // some vs every
    console.log(result);

}
//Q9.
{
    const result = students.reduce((prev, curr) => prev + curr.score, 0);
    console.log(result / students.length);
}
//Q10.
{
    const result = students
        .map((student) => student.score)
        .join(', ');
    console.log(result);
}

//Bonus
{
    const result = students
        .map((student) => student.score)
        .sort()
        .join(', ');
    console.log(result);
}
```
