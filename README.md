# 🔥Awesome Javascript Practice Exercises

> Click :star: if you like the project.

### Table of Contents

| No. | Questions                                                                                                                                                                         |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | [Write a JavaScript program to display the current day and time in the following format](#write-a-javascript-program-to-display-the-current-day-and-time-in-the-following-format) |
| 2   | [Write a JavaScript program to get the current date](#write-a-javascript-program-to-get-the-current-date)                                                                         |
| 3   | [Write a JavaScript program to find the area of a triangle](#write-a-javascript-program-to-find-the-area-of-a-triangle)                                                           |
| 4   | [Write a JavaScript program to calculate days left until next Christmas](#write-a-javascript-program-to-calculate-days-left-until-next-christmas)                                 |
| 5   | [Write a JavaScript exercise to get the extension of a filename](#write-a-javascript-exercise-to-get-the-extension-of-a-filename)                                                 |
| 6   | [Write a JavaScript program to compare two objects](#write-a-javascript-program-to-compare-two-objects)                                                                           |
| 7   | [Write a JavaScript program to convert an array of objects into CSV string](#write-a-javascript-program-to-convert-an-array-of-objects-into-csv-string)                           |
| 8   | [Write a JavaScript program to convert a number to array of digits](#write-a-javascript-program-to-convert-a-number-to-array-of-digits)                                           |
| 9   | [Write a JavaScript program to capitalize first letter of a string](#write-a-javascript-program-to-capitalize-first-letter-of-a-string)                                           |
| 10  | [Write a JavaScript program to determine if a variable is array](#write-a-javascript-program-to-determine-if-a-variable-is-array)                                                                   |
| 11  | [Write a JavaScript program to clone an array](#write-a-javascript-program-to-clone-an-array)                                                                                     |
| 12  | [Write a JavaScript program to reverse a string](#write-a-javascript-program-to-reverse-a-string)                                                                                     |

### Write a JavaScript program to display the current day and time in the following format

Sample Output :

<p>
Today is Friday.<br />
Current time is 12 PM : 12 : 22
</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function getTime(today) {
  const ampm = today.getHours() > 12 ? 'pm' : 'am';
  const hours = today.getHours() % 12 ? today.getHours() % 12 : 12;
  const minutes =
    today.getMinutes() < 10 ? `0${today.getMinutes()}` : today.getMinutes();
  const seconds =
    today.getSeconds() < 10 ? `0${today.getSeconds()}` : today.getSeconds();

  return `${hours} ${ampm} : ${minutes} : ${seconds}`;
}

function getDay(today) {
  return [
    'Sunday',
    'Monday',
    'Tuesday',
    'Wednesday',
    'Thursday',
    'Friday',
    'Saturday',
  ][today.getDay()];
}

const d = new Date();
console.log(`Today is ${getDay(d)}`);
console.log(`Current time is ${getTime(d)}`);
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to get the current date

mm-dd-yyyy <br />
mm/dd/yyyy <br />
dd-mm-yyyy <br />
dd/mm/yyyy

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function getDate(date, format, separator) {
  const data = {
    yyyy: today.getFullYear(),
    mm: today.getMonth() < 10 ? `0${today.getMonth()}` : today.getMonth(),
    dd: today.getDate() < 10 ? `0${today.getDate()}` : today.getDate(),
  };

  return format
    .split(separator)
    .map((char) => data[char])
    .join(separator);
}
const today = new Date();

console.log(getDate(today, 'mm-dd-yyyy', '-'));
console.log(getDate(today, 'mm/dd/yyyy', '/'));
console.log(getDate(today, 'dd-mm-yyyy', '-'));
console.log(getDate(today, 'dd/mm/yyyy', '/'));
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to find the area of a triangle

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function areaOfTriangle(a, b, c) {
  const s = (a + b + c) / 2;

  return Math.sqrt(s * (s - a) * (s - b) * (s - c));
}

console.log(areaOfTriangle(5, 6, 7));
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to calculate days left until next Christmas

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function daysUntilChristmas() {
  const today = new Date();
  const difference = new Date(today.getFullYear(), 11, 25) - new Date();
  const oneDayInNilliseconds = 1000 * 3600 * 24;

  return Math.ceil(difference / oneDayInNilliseconds);
}

console.log(daysUntilChristmas());
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript exercise to get the extension of a filename.

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function getExtension(filename) {
  return filename.substring(filename.lastIndexOf('.') + 1);
}

console.log(getExtension('hello-world.txt'));
console.log(getExtension('awesome.component.ts'));
console.log(getExtension('readme.md'));
console.log(getExtension('user.jsx'));
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to compare two objects

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function matches(source, target) {
  return Object.keys(source).every(
    (key) => target.hasOwnProperty(key) && target[key] === source[key]
  );
}

const car = {
  color: 'red',
  type: 'suv',
};

p1 = {
  name: 'john doe',
  car,
};
p2 = {
  name: 'john doe',
  car,
};
console.log(matches(p1, p2)); // true
console.log(matches(p1, { color: 'red', type: 'suv' })); // false
console.log(matches(p1, { name: 'john doe', car })); // true
console.log(matches(p1, { name: 'jane doe', car })); // false
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to convert an array of objects into CSV string

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function arrayToCSV(collection) {
  const headers = {};
  const rows = collection
    .map(
      (row) =>
        `${Object.keys(row)
          .map((key) => {
            headers[key] = key;

            return row[key];
          })
          .join(',')}`
    )
    .join('\n');

  return `${Object.keys(headers).join(',')}\n${rows}`;
}

console.log(
  arrayToCSV([
    { name: 'India', city: 'Pune', continent: 'Asia' },
    { name: 'Kenya', city: 'Mombasa', continent: 'Africa' },
    {
      name: 'Canada',
      city: 'Waterloo',
      continent: 'North America',
      captial: 'Ottawa',
    },
    { name: 'France', city: 'Paris', continent: 'Europe' },
  ])
);
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to convert a number to array of digits

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function numberToArray(num) {
  if (typeof num === 'number') {
    return `${num}`.split('').map((n) => parseInt(n));
  } else {
    return NaN;
  }
}

console.log(numberToArray(1234)); // [1, 2, 3, 4]
console.log(numberToArray('dsc')); // NaN
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to capitalize first letter of a string

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function ucfirst(str) {
  return `${str.charAt(0).toUpperCase()}${str.substring(1)}`;
}

console.log(ucfirst('javascript'));
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to determine if a variable is array

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
function is_array(param) {
  return Object.getPrototypeOf(param) === Array.prototype;
}

console.log(is_array([1, 2, 3, 4])); // true
console.log(is_array('abcd')); // false
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**

### Write a JavaScript program to clone an array

</p>
<details><summary><b>Solution:</b></summary>
<p>

```javascript
// using spread operator
function cloneArr(arr) {
  return [...arr];
}

console.log([1, 2, 3, 4, 5]);

// using for slice
function cloneArr(arr) {
  return arr.slice();
}

console.log([1, 2, 3, 4, 5]);

// using JSON object
function cloneArr(arr) {
  return JSON.parse(JSON.stringify(arr));
}

console.log([1, 2, 3, 4, 5]);

// using Array.from
function cloneArr(arr) {
  return Array.from(arr);
}

console.log([1, 2, 3, 4, 5]);
```

<p>
</details>

---

**[⬆ Back to Top](#table-of-contents)**
### Write a JavaScript program to reverse a string
<p>
<details><summary><b>Solution:</b></summary>
</p>

```javascript
function reverse(str) {
  return str.split('').reverse().join('');
}

// Test the function
const input = "Hello, World!";
const reversed = reverse(input);
console.log(reversed); 
// Output: "!dlroW ,olleH"
```

<p>
</details>

---