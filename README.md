# backfeed
Simple Bootstrap 3 form validation without JQuery

##Prerequisites

- Backfeed assumes that you're using the Bootstrap 3 CSS framework.
- Each input validated must be in its own form-group.
- The input must have a unique id (if invoking watchInputs).
- The form must have a unique id (if invoking watchForm).

##Usage

When the page is ready, call Backfeed on your form inputs in one of two ways:

- Backfeed.watchInputs() accepts an array of input ids.
- Backfeed.watchForm() accepts the id of the parent element of many inputs and activates form feedback on all of them.

```html
<body>
    <div class="container">
        <div id="test-form" class="form-horizontal">
            <div class="form-group">
                <input class="form-control" name="username" id="usernameInput" type="text" minlength="4" maxlength="11" required>
            </div>
            <div class="form-group">
                <input class="form-control" name="email" id="emailInput" type="email" minlength="4" maxlength="11" required>
            </div>
        </div>
        <div id="test-form2" class="form-horizontal">
            <div class="form-group">
                <input class="form-control" name="password" type="password" minlength="4" maxlength="11" required>
            </div>
            <div class="form-group">
                <input class="form-control" name="confirm" type="password" minlength="4" maxlength="11" required>
            </div>
        </div>
    </div>
    <script src="/path/to/backfeed.js"></script>
    <script>
        function ready(fn) {
            if (document.readyState != 'loading') {
                fn();
            } else {
                document.addEventListener('DOMContentLoaded', fn);
            }
        }

        ready(function go() {
            //invoke with array of ids, each corresponding to an input
            Backfeed.watchInputs(['usernameInput', 'emailInput']);
            
            //invoke with id of a form
            Backfeed.watchForm('test-form2');
        });
    </script>
</body>
```
