# Introduction

Web widgets powered by web components and React, published as UMD modules

On 20211010, version 2 is published.


## Quickstart - Examples

- Qia-Web-Widgets--Quickstart: <https://github.com/johannhuang/Qia-Web-Widgets--Quickstart>
- Qia-Web-Widgets--Quickstart--React: <https://github.com/johannhuang/Qia-Web-Widgets--Quickstart--React>
- Qia-Web-Widgets--Quickstart--Angular: <https://github.com/johannhuang/Qia-Web-Widgets--Quickstart--Angular>


## Quickstart - Step by Step

1. include React and ReactDOM

```html
<script src="https://unpkg.com/react@17/umd/react.production.min.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js" crossorigin></script>
```

or

```js
import React from 'react'
import ReactDOM from 'react-dom'

window.React = React
window.ReactDOM = ReactDOM
```

2. include QiaWidgets

```html
<script src="$base_url/qia-widgets.js" crossorigin></script>
```

or just the component used as

```html
<script src="node_modules/qia-widgets/qia-skeleton.js"></script>
```

or using JavaScript import

```js
import '$base_url/qia-widgets.js' // for side-effects

import Qia from '$base_url/qia-widgets.js' // for constructor function
const QiaSkeleton = Qia.Widgets.Skeleton
```

or

```js
import Qia from 'qia-widgets' // if transpiler e.g., webpack used
const QiaSkeleton = Qia.Widgets.Skeleton
```

3. use QiaWidgets

```html
<qia-skeleton></qia-skeleton>
```

or using JavaScript to construct and mount

```js
const qiaSkeletonContainer = document.createElement('div')
const qiaSkeleton = new QiaSkeleton({}, qiaSkeletonContainer)

document.body.appendChild(qiaSkeletonContainer)
```

or JSX or React.createElement() in React

```js
import Qia from 'qia-widgets'

const QiaSkeletonReactComponent = Qia.Widgets.Skeleton.ReactComponent

React.createElement(QiaSkeletonReactComponent)

<QiaSkeletonReactComponent />
```


## API

### HTML Custom Elements

- `<qia-paginator current="" total=""></qia-paginator>`
- `<qia-skeleton></qia-skeleton>`

### JavaScript Constructors

- `class QiaPaginator (props = {current, total}, containerElement)`
- `class QiaSkeleton (props = {}, containerElement)`

### React Components

- `class QiaPaginatorReactComponent extends React.Component (props = {current, total, onPageChange?, onPageChanged?})`
- `class QiaSkeletonReactComponent extends React.Component ()`
