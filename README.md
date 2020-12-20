# countdown
Countdown APP made with Javascript

Languages: HTML/CSS/Javascript

Notable Features:

Uses local storage to keep countdown going even when refreshing or leaving page.

```javascript
function restorePrevCount() {
    if (localStorage.getItem('countdown')) {
        inputContainer.hidden = true;
        savedCountdown = JSON.parse(localStorage.getItem('countdown'));
        countdownTitle = savedCountdown.title;
        countdownDate = savedCountdown.date;
        countdownValue = new Date(countdownDate).getTime();
        updateDOM();
    }
}
```

Displays Time left until date in UTC time.

```javascript
e.preventDefault();
    countdownTitle = e.srcElement[0].value;
    countdownDate = e.srcElement[1].value;
    savedCountdown = {
        title: countdownTitle,
        date: countdownDate,
    };
    localStorage.setItem('countdown', JSON.stringify(savedCountdown));
```

Uses preventDefault from allowing page to refresh when submitted.


Countdown function runs every second using setInterval();

JSON.stringify to let the localStorage read and contain object and then JSON.parse to bring it back out when loading page.

