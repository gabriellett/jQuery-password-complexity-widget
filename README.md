# jQuery-password-complexity-widget

jQuery widget for password complexity validation

## Dependencies:

You must have fontawesome configurated in your project if you want 'checkes' and 'Xes' on your password validations.

## Usage Example:

### Using the default configuration:

Where you want your validations to appear, set the element id to `password_validations` , this option may be overriden by setting `validationsDiv` to the jQuery element that represents your div. You may also set the submit button, this widget will disable and enable the submit button according to the validity of the password. This may be set using the `data-submit-button` attribute, passing the selector for the button, or you may also ovveride the option `submitButton`

Add `data-validate-complexity=true` to your password field. If you have a password confirmation field, add a `data-confirmation-field` attribute and set its value to the confirmation field CSS selector, for example, `data-confirmation-field="#user_password_confirmation"`

	$("[data-validate-complexity='true'").each(function(){
		$(this).validatePassword({
			validations: {
				minUppercaseChars: {
					message: "At least one uppercase letter",
					regex: "^(?=.*[A-Z]+).+$"},
				minLowercaseChars: {
					message: "At least one lowercase letter",
					regex: "^(?=.*[a-z]+).+$"},
				minNumbers: {
					message: "At least one number",
					regex: "^(?=.*[0-9]+).+$"},
				minSpecialChars: {
					message: "At least one special letter (!$%@#)",
					regex: "^(?=.*[!$%@#]+).+$"},
				minLength: {
					message: "At least 8 characters"
					regex: ".{8,}$"}
			}
		});
	});

The `validations` inner obj beeing your validation, containg the regex to be validated and the helper message.

## Options


The following default options can be overriden:

	options:{
		passwordConfirmation: null,
		validationsDiv: $("#password_validations),
		validations: {},
		submitButton: null
	}

#### `passwordConfirmation`:

The password confirmation field selector, if you don't need to confirm your password, leave this option null.

#### `validationsDiv`:

This div is where your validations are going to appear.

#### `validations`:

Your validations, as described in the example.

#### `submitButton`:

The button that will be disabled and enabled according to the password validity.




