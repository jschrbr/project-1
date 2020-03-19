<h1 align="center">Welcome to food-hound <img width="40px" src="./assets/images/material-hound.png">
</h1>
<p>
  <img alt="Version" src="https://img.shields.io/badge/version-01.00-blue.svg?cacheSeconds=2592000" />
  <a href="https://github.com/jschrbr/food-hound" target="_blank">
    <img alt="Documentation" src="https://img.shields.io/badge/documentation-yes-brightgreen.svg" />
  </a>
</p>

> A simple single page application for looking up recipes. The application also has the option to convert the currency of the estimated prices.

### 🏠 [Homepage](https://github.com/jschrbr/food-hound)

### ✨ [Demo](https://jschrbr.github.io/food-hound/)

## Usage

```sh
How to use the app
```

## Page layout

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
```

```css
body {
  margin: 20px;
}
```

## Recipe lookup

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
```

```js
let one = 1;
console.log(one);
```

## Incredient lookup

```html
<!DOCTYPE html>
<html>
  <head></head>
  <body></body>
</html>
```

```js
let one = 1;
console.log(one);
```

## Get exchange rate

### Dropdown component

The below code defines the dropdown component from the materialize css library.

The element must be contained inside an input field.

```html
<div class="input-field red accent-4 amber-text">
  ...
  <!-- code goes here -->
  ...
</div>
```

The input uses materialize classes to match the site theme.

```html
.red .accent-4 .amber-text
```

select tag is declared with nest options, each option holds a value used when querying https://free.currencyconverterapi.com/.

```html
<select data-exch-rate="">
  <option value="0" disabled selected> $</option>
  <option class="amber-text" value="AUD">AUD</option>
  <option value="USD">USD</option>
  <option value="GBP">GPB</option>
</select>
```

### The structure

First we define some constants used throughout the code.

```js
const currencySelect = $("select");
const selectSel = currencySelect.formSelect()[0];
```

Then we define the function then call it immediately.

```js
function getExchRate() {
  let currency = localStorage.getItem("currency");
  if (currency) {
    selectSel.value = currency;
  } else {
    currency = "AUD";
  }
  currencySelect.formSelect();
  url = "currency url";

  // Make API call
}

getExchRate();
```

The code intially ensures there is a currency value for the api call. It does so by checking the `localStorage` for a previously selected option, otherwise assigning a default value `"AUD"`.

The below jqueryy function renders the dropdown element, incase a value was retrieved from local storage

```js
currencySelect.formSelect();
```

### The call

The url query string is built with the validated currency, and used in the below code.

```js
$.ajax({
  url: url,
  method: "GET"
}).then(function(resp) {
  let rate = Object.values(resp)[0];
  selectSel["data-exch-rate"] = rate;
});
```

The exchange rate is then set to an attribute names `"data-exch-rate"`

### The listener

Finally we setup a listener, to monitor for a change in the dropdown selection.

```js
currencySelect.on("change", function(e) {
  localStorage.setItem("currency", e.target.value);
  getExchRate();
});
```

The selection is saved to local storage, and the `getExchRate()` function is called. Where the seletion is retrieved from local stroage.

## Contributors

### James Schreiber

- Website: https://jschrbr.github.io/
- Github: [@jschrbr](https://github.com/jschrbr)
- LinkedIn: [@techsmechs](https://linkedin.com/in/techsmechs)

### Name

- Website: https://{placeholder}.github.io/
- Github: [@{placholder}](https://github.com/{placholder})
- LinkedIn: [@{placholder}](https://linkedin.com/in/{placholder})

### Name

- Website: https://{placeholder}.github.io/
- Github: [@{placholder}](https://github.com/{placholder})
- LinkedIn: [@{placholder}](https://linkedin.com/in/{placholder})

### Name

- Website: https://{placeholder}.github.io/
- Github: [@{placholder}](https://github.com/{placholder})
- LinkedIn: [@{placholder}](https://linkedin.com/in/{placholder})

## 🤝 Contributing

Contributions, issues and feature requests are welcome!<br />Feel free to check [issues page](https://github.com/jschrbr/food-hound/issues).

## Show your support

Give a ⭐️ if this project helped you!

<a href="https://www.patreon.com/techsmechs">
  <img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="160">
</a>

---

_This README was generated with ❤️ by [readme-md-generator](https://github.com/kefranabg/readme-md-generator)_
