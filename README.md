# Awesome Javascript Practice Exercises

> Click :star: if you like the project.

### Table of Contents

| No. | Questions                                                                                                                                                                         |
| --- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | [Write a JavaScript program to display the current day and time in the following format](#write-a-javascript-program-to-display-the-current-day-and-time-in-the-following-format) |
| 2   | [Write a JavaScript program to get the current date](#write-a-javascript-program-to-get-the-current-date)                                                                         |
| 3   | [Write a JavaScript program to find the area of a triangle](#write-a-javascript-program-to-find-the-area-of-a-triangle)                                                           |
| 3   | [Write a JavaScript program to calculate days left until next Christmas](#write-a-javascript-program-to-calculate-days-left-until-next-christmas)                                 |

### Write a JavaScript program to display the current day and time in the following format

Sample Output :

<p>
Today is Friday.<br />
Current time is 10 PM : 30 : 38
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
