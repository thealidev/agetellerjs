# A JS That Auto Keep Updating Your Age
## Add it
```
<h4><center>I Am <b id="age"></b> Years Old.</center></h4>
<script>
  const day = 24 * 60 * 60 * 1000;
  const age = document.getElementById("age");

  round_to = function (precision, value) {
    value = parseFloat(value);
    power_of_ten = 10 ** precision;
    return Math.round(value * power_of_ten) / power_of_ten;
  }

  day_diff = function (d1, d2) {
    /* totally not borrowed from kristians page */
    return (d2 - Date.parse(d1)) / day;
  }

  function update_age() {
    age.innerHTML = round_to(8, day_diff('Dec 24, 2003 12:00:00', new Date()) / 365);
  }

  update_age();
  setInterval(function () {
    update_age();
  }, 100)
</script>
```
### Change `Dec 24, 2003 12:00:00` Accourding To Your Birthday Format
