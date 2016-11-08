![react-times](./intro_src/react_times.png)

[![npm version](https://badge.fury.io/js/react-times.svg)](https://badge.fury.io/js/react-times)
[![Build Status](https://travis-ci.org/ecmadao/react-times.svg?branch=master)](https://travis-ci.org/ecmadao/react-times) [![Coverage Status](https://coveralls.io/repos/github/ecmadao/react-times/badge.svg?branch=master)](https://coveralls.io/github/ecmadao/react-times?branch=master) [![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg)](http://standardjs.com) [![react-times](http://img.shields.io/npm/dm/react-times.svg)](https://www.npmjs.com/package/react-times) [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/ecmadao/react-times/master/LICENSE)

[![NPM](https://nodei.co/npm/react-times.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/react-times)

> A time picker react-component, no jquery-rely, writing in es6 standrad style.

![react-times](./intro_src/react-times.gif)

## Play in local

```bash
$ git clone https://github.com/ecmadao/react-times.git

$ npm install

$ npm run storybook
```

## Install

dependencies:

- [`moment`](https://github.com/moment/moment/)
- [`react`](https://github.com/facebook/react)
- [`react-dom`](https://github.com/facebook/react)

> No jQuery rely 😤😤😤

So generally speaking, you should already have `react` & `react-dom` dependencies in your project. If not:

```bash
$ npm install react react-dom --save-dev
# and
$ npm install react-times --save-dev
```

## Usage

This component has two themes now: Material Theme by default , or Classic Theme.

> Always remember import css file when you use react-times

```javascript
// basic usage
// in some react component
import React from 'react';
import TimePicker from 'react-times';

// use material theme
import 'react-times/css/material/default.css';
// or you can use classic theme
import 'react-times/css/classic/default.css';

export default class SomeComponent extends React.Component {
  // do some work
  onHourChange(hour) {
    // do something
  }

  onMinuteChange(minute) {
    // do something
  }

  onTimeChange(time) {
    // do something
  }

  onFocusChange(focusStatue) {
    // do something
  }

  render() {
    <TimePicker
      onFocusChange={this.onFocusChange.bind(this)}
      onHourChange={this.onHourChange.bind(this)}
      onMinuteChange={this.onMinuteChange.bind(this)}
      onTimeChange={this.onTimeChange.bind(this)}
    />
  }
}
```

> See more examples here:

```javascript
// some config example
render() {
  <TimePicker 
  	colorPalette="dark" // main color, default "light"
  	focused={true} // whether to show timepicker modal after rendered. default false
  	withoutIcon={true} // whether to has time icon on button, default false
  	defaultTime="13:05" // initial time, default current time
  />
}
```

> For more detail usage, you can visit [example](https://github.com/ecmadao/react-times/tree/master/examples) or see the source code.

## Show time

> 24 hours mode with Material Theme, light color by default

![24HoursMode](./intro_src/24HoursMode.png)

> 12 hours mode with Material Theme, light color by default

![12HoursMode](./intro_src/12HoursMode.png)

> 24 hours mode with Material Theme, dark color

![DarkColor](./intro_src/DarkColor.png)

> 24 hours mode with Classic Theme, light color by default

![24HoursMode-ClassicTheme](./intro_src/24HoursMode-ClassicTheme.png)

> 24 hours mode with Classic Theme, dark color

![24HoursMode-ClassicTheme-dark](./intro_src/24HoursMode-ClassicTheme-dark.png)

## APIs

### Props

- `defaultTime`

> Initial time, must be a string, with `${hour}:${minute}` format, default now (by using `moment()`):

```javascript
// React.PropTypes.string
defaultTime="11:11"
defaultTime="11:01"
defaultTime="1:01"
defaultTime="1:1"
```

- `focused`

> Whether the timepicker pannel is focused or not when it did mount. Default `false`

```javascript
// React.PropTypes.bool
focused={false}
focused={true}
```

- `withoutIcon`

> Whether the timepicker has a svg icon. Default `false`.

```javascript
// React.PropTypes.bool
withoutIcon={true}
```

- `colorPalette`

> The main color palette of picker pannel. Default `light`.

```javascript
// React.PropTypes.string
colorPalette="dark"
colorPalette="light"
```

- `timeMode`

> Support "12" or "24" hours mode.

```javascript
// React.PropTypes.string or React.PropTypes.number
timeMode="24"
timeMode=24
timeMode="12"
timeMode=12
```

- `onFocusChange`

`React.PropTypes.func`

> The callback func when component `focused` state is changed.

- `onHourChange`

`React.PropTypes.func`

> The callback func when component `hour` state is changed.

```javascript
onHourChange(hour) {
  // ...
}
```

- `onMinuteChange`

`React.PropTypes.func`

> The callback func when component `minute` state is changed.

```javascript
onMinuteChange(minute) {
  // ...
}
```

- `onTimeChange`

`React.PropTypes.func`

> The callback func when component `hour` or `minute` or `AM/PM` state is changed.

```javascript
onTimeChange(time) {
  // ...
}
```

## Article

- [一言不合造轮子--撸一个ReactTimePicker](https://github.com/ecmadao/Coding-Guide/blob/master/Notes/React/ReactJS/Write%20a%20React%20Timepicker%20Component%20hand%20by%20hand.md)

## Todos

- Test

  - [x] TimePicker Component
  - [x] PickerDragHandler Component
  - [x] PickerPointGenerator Component
  - [x] MaterialTheme Component
  - [x] TwelveHoursTheme Component
  - [x] PickerPoint Component
  - [ ] OutsideClickHandler Component

  - [x] utils test

- Color Palette (Now It has light and dark color)

  - [x] light
  - [x] dark
  - [ ] colorful

- Themes

  - [x] Material Theme
  - [x] Classical Theme

- Mode

  - [x] 12h mode
  - [x] 24h mode

- Animations

## Thx

Thanks to the Airbnb's open source project: [react-dates](https://github.com/airbnb/react-dates), I have learn a lot from that. Thanks.

## License

```
MIT License

Copyright (c) 2016 ecmadao

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
