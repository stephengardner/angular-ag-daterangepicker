# Date Range Picker for Angular and Bootstrap
### Fixed outstanding issues from previous angular daterangepicker.
![Dependencies](https://david-dm.org/fragaria/angular-daterangepicker.png)

Angular.js directive for Dan Grossmans's [Bootstrap Datepicker](https://github.com/dangrossman/bootstrap-daterangepicker).

[DEMO](http://fragaria.github.io/angular-daterangepicker/)

**Beware: Use [Bootstrap Datepicker](https://github.com/dangrossman/bootstrap-daterangepicker) v 2.0.0 and newer!**

![Date Range Picker screenshot](http://i.imgur.com/zDjBqiS.png)

## Installation via Bower
The easiest way to install the picker is:
```
bower install ag-angular-daterangepicker --save
```
## Manual installation
This directive depends on [Bootstrap Datepicker](https://github.com/dangrossman/bootstrap-daterangepicker), [Bootstrap](http://getbootstrap.com), [Moment.js](http://momentjs.com/) and [jQuery](http://jquery.com/).
Download dependencies above and then use [minified](js/angular-daterangepicker.min.js) or [normal](angular-daterangepicker.js) version.

## Basic usage
Assuming that bower installation directory is `bower_components`. In case of other installation directory, please update paths accordingly.

```
<script src="bower_components/jquery/jquery.js"></script>
<script src="bower_components/angular/angular.js"></script>
<script src="bower_components/momentjs/moment.js"></script>
<script src="bower_components/bootstrap-daterangepicker/daterangepicker.js"></script>
<script src="bower_components/angular-daterangepicker/js/angular-daterangepicker.js"></script>

<link rel="stylesheet" href="bower_components/bootstrap/dist/css/bootstrap.css"/>
<link rel="stylesheet" href="bower_components/bootstrap-daterangepicker/daterangepicker-bs3.css"/>
```

Declare dependency:

```
App = angular.module('app', ['daterangepicker']);
```

Prepare model in your controller. The model **must** have `startDate` and `endDate` attributes:

```
exampleApp.controller('TestCtrl', function ($scope) {
	$scope.datePicker.date = {startDate: null, endDate: null};
}
```


Then in your HTML just add attribute `date-range-picker` to any input and bind it to model.

```
<div ng-controller="TestCtrl">
<input date-range-picker class="form-control date-picker" type="text" ng-model="datePicker.date" />
</div>
```

See `example.html` for working demo.

### Mind the dot!
Do not forget to add a dot (.) in your model object to avoid [issues with scope inheritance](https://github.com/angular/angular.js/wiki/Understanding-Scopes). E.g. use `$scope.datePicker.date` instead of `$scope.date`.

## Advanced usage
Min and max value can be set via additional attributes:

```
<input date-range-picker class="form-control date-picker" type="text" ng-model="date" min="'2014-02-23'" max="'2015-02-25'"/>
```

The date picker can be further customized by passing in the `options` attribute.

```
<input date-range-picker class="form-control date-picker" type="text" ng-model="date"
min="'2014-02-23'" max="'2015-02-25'" options="{separator: ":"}"/>
```

Optionally, event handlers can be passed in through the `eventHandlers` attribute of `options`.

```
<input date-range-picker class="form-control date-picker" type="text" ng-model="date"
options="{eventHandlers: {'show.daterangepicker': function(ev, picker) { ... }}}"/>
```

All event handlers from the Bootstrap daterangepicker are supported. For reference, the complete list is below:

`show.daterangepicker`: Triggered when the picker is shown

`hide.daterangepicker`: Triggered when the picker is hidden

`showCalendar.daterangepicker`: Triggered when the calendar is shown

`hideCalendar.daterangepicker`: Triggered when the calendar is hidden

`apply.daterangepicker`: Triggered when the apply button is clicked

`cancel.daterangepicker`: Triggered when the cancel button is clicked

## Links
See [original documentation](https://github.com/dangrossman/bootstrap-daterangepicker).


[![Throughput Graph](https://graphs.waffle.io/fragaria/angular-daterangepicker/throughput.svg)](https://waffle.io/fragaria/angular-daterangepicker/metrics)

