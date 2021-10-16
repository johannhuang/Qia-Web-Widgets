# Introduction

Web widgets powered by web components and React, published as UMD modules

---

Documentation is available at <https://github.johannhuang.com/Qia-Web-Widgets/>.

On 20211016, version 4 is published.


## APIs

### JavaScript Constructors

- `class QiaMarkDownText (containerElement: HTMLElement, optionsObject? : { readOnly?: boolean; canFullScreen?: boolean } = {})`
- `class QiaPaginator (containerElement, optionsObject = { current, total })`
- `class QiaSkeleton (containerElement)`

### HTML Custom Elements

- `<qia-paginator current="" total=""></qia-paginator>`
	* `class QiaPaginator.HTMLElement extends HTMLElement`
- `<qia-skeleton></qia-skeleton>`
	* `class QiaSkeleton.HTMLElement extends HTMLElement`

### React Components

- `class QiaPaginator.ReactComponent extends React.Component (props = { current, total, onPageChange?, onPageChanged? })`
- `class QiaSkeleton.ReactComponent extends React.Component ()`


## Installation

1. Download files from GitHub or find links on CDN such as UNPKG.com, and then import as HTML scirpts
2. `npm install qia-widgets` from <https://www.npmjs.com/package/qia-widgets>


## Quickstart - Step by Step

1. include React and ReactDOM

```html
<script src="https://unpkg.com/react@17/umd/react.production.min.js" crossorigin></script>
<script src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js" crossorigin></script>
```

2. include Qia.Widgets

for all available widgets as HTML scripts

```html
<script src="$base_url/qia.widgets.js" crossorigin></script>
<!-- .widgets is the namespace just like .audio is the namespace for audio-player; web components are named without widgets in-between, such as qia-paginator -->
```

for just the widgets needed as HTML scripts

```html
<script src="node_modules/qia-widgets/qia-skeleton.js"></script>
```

for all available widgets in JavaScript with a bare module resolver

```js
import QiaWidgets from 'qia-widgets'
const QiaSkeleton = QiaWidgets.Skeleton
```

for just the widgets needed in JavaScript with a bare module resolver

```js
import QiaSkeleton from 'qia-widgets/qia-skeleton'
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
const QiaSkeletonReactComponent = QiaSkeleton.ReactComponent

React.createElement(QiaSkeletonReactComponent)

<QiaSkeletonReactComponent />
```


## Quickstart - Examples

- Qia-Web-Widgets--Quickstart: <https://github.com/johannhuang/Qia-Web-Widgets--Quickstart>
- Qia-Web-Widgets--Quickstart--React: <https://github.com/johannhuang/Qia-Web-Widgets--Quickstart--React>
- Qia-Web-Widgets--Quickstart--Angular: <https://github.com/johannhuang/Qia-Web-Widgets--Quickstart--Angular>


## Dependencies

* QiaSkeleton, QiaPaginator
	* React and ReactDOM (They are not bundled in the module.)
* QiaMarkDownText
	* [Font Awesome](https://www.npmjs.com/package/font-awesome) (It is not bundled in the module.)
	* [SimpleMDE](https://www.npmjs.com/package/simplemde) (It is bundled in the module.)
