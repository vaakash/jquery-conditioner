# jQuery Conditioner

This plugin allows to conditionally display elements based on input element values.

### Use case

This plugin is really useful in forms where we want to conditionally show fields based on some input element value. Consider the below example, where I want to show the advanced options form when advanced option is selected

##### HTML:
```
Settings:
<label><input type="radio" value="normal" name="settings"/> Normal</label>
<label><input type="radio" value="advanced" name="settings"/> Advanced</label>

<div class="advanced-options" data-condr-input="[name=settings]" data-condr-value="advanced" data-condr-action="simple?show:hide" data-condr-events="click">
    Some advanced options fields
</div>

<script>$('.advanced-options').conditioner();</script>
```
In the above example the advanced-options form will be visible when advanced is selected. Everything initialized through inline data param !

### External Options

```
$('.elementToConditionalize').conditioner({
        // Check multiple conditions from different inputs. Condition will pass only if all of them satisfy
		conditions: [
			{
				input: '.textbox',
				type: 'simple', // If value is a pattern to match then type is 'pattern'
				value: 'hey'
			},
			{
				input: '[name=agreecheck]',
				type: 'simple',
				value: 'agree'
			},
			{
				input: '.checkbox'
			},
		],
		events: 'click keyup',
		onTrue: function(){  $(this).fadeIn( 'slow' );  },
		onFalse: function(){  $(this).slideUp( 'slow' );  }
	});
```

### Documentation

In the works ...

### License

Copyright (c) 2015 [Aakash Chakravarthy](http://www.aakashweb.com/), released under the MIT License.