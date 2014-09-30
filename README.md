# component.fullscreen-form

An experimental fullscreen form concept where the idea is to allow distraction-free form filling with some fancy animations when moving between form fields.

Inspired by [FULLSCREEN FORM INTERFACE](http://tympanus.net/codrops/2014/07/30/fullscreen-form-interface/)

## Example

Check out `example/index.html`, the example javascript for the example page is `resources/js/example_src.js`

## Installation

```
$ npm install periodicjs.component.fullscreen-form
```

The fullscreen-form component is a browserified javascript module.

## Usage

*JavaScript*
```javascript
var FForm = require('periodicjs.component.fullscreen-form');
window.FForm = FForm;
window.addEventListener('load', function() {
  var formWrap = document.getElementById('fs-form-wrap');
  new window.FForm(formWrap, {
    onReview: function() {
      classie.add(document.body, 'overview'); // for demo purposes only
    }
  });
}, false);
```

*HTML*
```html
<html>
	<head>
  	<title>Your Page</title>
  	<link rel="stylesheet" type="text/css" href="[path/to]/component.fullscreen-form.css">
  	<script src='[path/to/browserify/bundle].js'></script>
	</head>
	<body>
		<div class="container">
          <div class="fs-form-wrap" id="fs-form-wrap">
            <form id="myform" class="fs-form fs-form-full" autocomplete="off">
              <ol class="fs-fields">
                <li>
                  <label class="fs-field-label fs-anim-upper" for="q1">What's your name?</label>
                  <input class="fs-anim-lower" id="q1" name="q1" type="text" placeholder="Dean Moriarty" required/>
                </li>
                <li>
                  <label class="fs-field-label fs-anim-upper" for="q2" data-info="We won't send you spam, we promise...">What's your email address?</label>
                  <input class="fs-anim-lower" id="q2" name="q2" type="email" placeholder="dean@road.us" required/>
                </li>
                <li data-input-trigger>
                  <label class="fs-field-label fs-anim-upper" for="q3" data-info="This will help us know what kind of service you need">What's your priority for your new website?</label>
                  <div class="fs-radio-group fs-radio-custom clearfix fs-anim-lower">
                    <span>
                      <input id="q3b" name="q3" type="radio" value="conversion" />
                      <label for="q3b" class="radio-conversion">Sell things</label>
                    </span>
                    <span>
                      <input id="q3c" name="q3" type="radio" value="social" />
                      <label for="q3c" class="radio-social">Become famous</label>
                    </span>
                    <span>
                      <input id="q3a" name="q3" type="radio" value="mobile" />
                      <label for="q3a" class="radio-mobile">Mobile market</label>
                    </span>
                  </div>
                </li>
                <li>
                  <label class="fs-field-label fs-anim-upper" for="q4">Describe how you imagine your new website</label>
                  <textarea class="fs-anim-lower" id="q4" name="q4" placeholder="Describe here"></textarea>
                </li>
                <li>
                  <label class="fs-field-label fs-anim-upper" for="q5">What's your budget?</label>
                  <input class="fs-mark fs-anim-lower" id="q5" name="q5" type="number" placeholder="1000" step="100" min="100" />
                </li>
              </ol>
              <!-- /fs-fields -->
              <button class="fs-submit" type="submit">Send answers</button>
            </form>
            <!-- /fs-form -->
          </div>
          <!-- /fs-form-wrap -->
        </div>
	</body>
</html>
```

##API

####Full API [DOCUMENTATION](https://github.com/typesettin/component.fullscreen-form/blob/master/doc/api.md)

```javascript
new window.FForm(formWrap, {
  onReview: function() {
    classie.add(document.body, 'overview'); // for demo purposes only
  }
});
```
##Development
*Make sure you have grunt installed*
```
$ npm install -g grunt-cli
```

Then run grunt watch
```
$ grunt watch
```

##Notes
* The less file is located in `resources/stylesheets`