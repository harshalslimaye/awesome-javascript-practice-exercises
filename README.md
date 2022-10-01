# Awesome Javascript Practice Exercises

> Click :star: if you like the project.

### Table of Contents

| No. | Questions                                                                                                                                                                           |
| --- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | [Write a JavaScript program to display the current day and time in the following format.](#write-a-javascript-program-to-display-the-current-day-and-time-in-the-following-format.) |

1. ### Write a JavaScript program to display the current day and time in the following format.

Sample Output :

<p>
Today is Friday.<br />
Current time is 10 PM : 30 : 38
</p>
<details><summary><b>Solution:</b></summary>
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
][today.getday()];
}

const d = new Date();
console.log(`Today is ${getDay(d)}`);
console.log(`Current time is ${getTime(d)}`);

```
</details>
```
