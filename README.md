# gpx2czml
[![Build Status](https://travis-ci.org/trustyoo86/gpx2czml.svg?branch=master)](https://travis-ci.org/trustyoo86/gpx2czml)


*gpx2czml is updated 1.0.0. previous version is deprecated.*

javascript gpx to czml data convert module

## 개요(Summary)

이 모듈은 gpx 데이터를 czml 데이터로 변환해주는 javascript 모듈입니다.<br/>
This module is a javascript module that converts gpx data to czml data.

czml로 변환한 데이터는 Cesium.js에 활용될 수 있습니다.<br/>
The data converted to czml can be used for Cesium.js.

## 설치(Setup)

## Browser Support

- IE : 10+
- Chrome, Firefox, Safari


#### HTML
```html
<script src="path/to/gpx2czml.js"></script>
```

#### npm or common js

```bash
$npm install gpx2czml
```

javascript install

```js
//pure javascript
var gpx2czml = require('gpx2czml');
```

## 사용법(Usage)

#### gpx2czml.js

gpx2czml.js를 사용하여 gpx를 czml로 컨버팅 하기 위해서는 두가지 방법으로 사용하실 수 있습니다.<br/>
There are two ways to convert gpx to czml using gpx2czml.js.

### 1) asyncFromAjax

http request를 통해서 gpx를 czml로 변환하실 수 있습니다. 변환하는 방법은 url 및 callback function을 통해서 가능합니다.<br/>
You can do this through the url and callback functions.

```js
gpx2czml.asyncFromAjax('your http request path', function (isError, result) {
  if (isError) {

  } else {
    //czml object data result
    console.log('result is : ', result);
  }
});
```

async function에서 사용되는 파라미터는 다음과 같습니다.<br/>
The parameters used in the async function are as follows

- url : 호출하고자 하는 http url<br/>
The http url you want to call

callback function에서 반환되는 파라미터는 다음과 같습니다.<br/>
The parameters returned by the callback function are:

- isError : 에러 여부, 처리 과정 중에 에러가 발생하면 true로 반환됩니다.<br/>
If an error occurs during processing, it is returned as true.

- result : 에러가 나지 않는다면, czml JSON object를 반환합니다.<br/>
If there are no errors, the czml JSON object is returned.

### 2) asyncFromFile

input file 태그를 사용하여 gpx 파일을 업로드 하여 사용하실 수 있습니다. 사용 방법은 다음과 같습니다.
You can use gpx2czml using input tag. Here is usage that use input tag.

###### HTML
```html
<input type="file" onchange="handleEvent(event)"/>
```

###### javascript

```js
function handleEvent(e) {
  gpx2czml.asyncFromFile(e, function (isError, czml) {
    if (isError) {

    } else {
      //czml object data result
      console.log('result is : ', result);
    }
  });
}
```

사용되는 파라미터는 async function과 동일합니다.<br/>
The parameters used are the same as the async function.

## 문의 (Contact)

* email: trustyoo86@gmail.com