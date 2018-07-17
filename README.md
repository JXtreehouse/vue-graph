# vue-graph

> A vue component library based on the [jui charts](http://jui.io/?p=chart) available in vuejs.

[![forthebadge](http://forthebadge.com/images/badges/built-with-love.svg)](http://forthebadge.com)
[![forthebadge](http://forthebadge.com/images/badges/made-with-vue.svg)](http://forthebadge.com)
[![forthebadge](http://forthebadge.com/images/badges/uses-js.svg)](http://forthebadge.com)

## Installation

### NPM
```bash
npm install --save vue-graph
```

### Browser
Just download `dist/vue-graph.js` and include it in your HTML file:

```html
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/2.5.16/vue.js"></script>
<script src="https://cdn.rawgit.com/juijs/vue-graph/2216ae2f/dist/vue-graph.js"></script>
```

### ES Modules

```js
import Vue from 'vue'
import VueGraph from '/src/vue-graph.js'

Vue.use(VueGraph)
```

## Usage

Unlike other chart components, vue-graphs have child nodes in the chart called widgets. The widget is used as an additional function of charts such as chart title, legend, tooltip.

The following is a link you can test with [CodePen](https://codepen.io/collection/nWpqoB/).

![](https://cdn.rawgit.com/juijs/vue-graph/9517572b/examples/images/1.png)

```html
<div id="app">
    <graph-bar
            :width="600"
            :height="400"
            :axis-min="0"
            :axis-max="50"
            :labels="[ '1Q', '2Q', '3Q', '4Q' ]"
            :values="values">
        <note :text="'Bar Chart'"></note>
        <tooltip :names="names" :position="'left'"></tooltip>
        <legends :names="names" :filter="true"></legends>
    </graph-bar>
</div>
```
In the following code, the chart is prefixed with 'graph-' for each type. The widget can be added as a child node of the chart, unlike a chart, was named without a prefix.

The vue-graph can be combined with charts and widgets for a variety of visualizations. This is a very flexible and scalable structure.
```js
var vm = new Vue({
    el: "#app",
    data: {
        names: [ "MS", "Apple", "Google" ],
        values: [
            [ 10, 5, 5, 5 ],
            [ 40, 10, 10, 10 ],
            [ 30, 30, 30, 30 ]
        ]
    }
});
```

## Implemented chart list

There are many charts that have not yet been migrated. We are going to continue.

 - [Bar Chart](https://codepen.io/seogi1004/pen/WKrVLx)
 - [Bar Chart (Reverse)](https://codepen.io/seogi1004/pen/xJZvva)
 - [Stack Bar Chart](https://codepen.io/seogi1004/pen/djMbGE)
 - [Stack Bar Chart (Reverse)](https://codepen.io/seogi1004/pen/oMxvLR)
 - [Stack Bar Cahrt (Full Mode)](https://codepen.io/seogi1004/pen/xJVKVm)
 - [Line Chart](https://codepen.io/seogi1004/pen/jpqNPm)
 - [Line Chart (Reverse)](https://codepen.io/seogi1004/pen/MBygar)
 - [Line Chart (Date+Block)](https://codepen.io/seogi1004/pen/qyZWEL)
 - [3D-Bar Chart](https://codepen.io/seogi1004/pen/GBoVPV)
 - [3D-Line Chart](https://codepen.io/seogi1004/pen/PBZMEr)
 - [Scatter Chart](https://codepen.io/seogi1004/pen/YjqKym)
 - [Bubble Chart](https://codepen.io/seogi1004/pen/qyZWBL)
 - [Area Chart](https://codepen.io/seogi1004/pen/qybeMy)
 
## Props

### Common
| Name | Type | Required | Watch | Default | Description |
| ---------------- | -------------- | -------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| theme | String | false | false | `jennifer` | Supports a total of five themes (jennifer, dark, pastel, gradient, pattern) |
| styles | Object | false | false | `undefined` | Options to customize chart theme properties ([Style Tab](http://chartplay.jui.io/)) |
| colors | Array, Function | false | false | `undefined` | Options to change the list of colors defined by chart theme ([Style Tab](http://chartplay.jui.io/)) |
| clip | Boolean | false | false | false | Option to cut if the drawing element is out of the chart range |
| format | Function | false | true | `undefined` | A callback function that allows you to customize the axis values of the chart |
| width | Number | true | true | `undefined` | The width of the chart |
| height | Number | true | true | `undefined` | The height of the chart |
| paddingTop | Number | false | false | 50 | Top padding of the chart |
| paddingRight | Number | false | false | 50 | Right padding of the chart |
| paddingBottom | Number | false | false | 50 | Bottom padding of the chart |
| paddingLeft | Number | false | false | 50 | Left padding of the chart |
| labels | Array | true | true | `undefined` | Label of chart data |
| values | Array | false | true | `undefined` | It is a chart data value, and the format may be different for each chart type |

### Common (X-Y Axis)
| Name | Type | Required | Watch | Default | Description |
| ---------------- | -------------- | -------------- | ----------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| axisMin | Number | false | false | 0 | Miniimum value for the chart axis |
| axisMax | Number | false | false | 0 | Maximum value for the chart axis |
| axisStep | Number | false | false | 10 | Display interval of chart axis value |
| axisXStyle | String | false | false | `solid` | Line style for chart x-axis area (solid, dotted, gradient, hidden) |
| axisYStyle | String | false | false | `solid` | Line style for chart y-axis area (solid, dotted, gradient, hidden) 
| axisXPosition | String | false | false | `bottom` | Chart x-axis position (bottom, top) |
| axisYPosition | String | false | false | `left` | Chart y-axis position (left, right) |
| axisReverse | Boolean | false | false | false | Replace the x and y axis positions |
| axisFullMode | Boolean | false | false | false | Draw a chart drawing element full of the axis label area. |
| axisInterval | Number | false | false | 1000 * 60 * 60 | It is the label value display interval of the date type (Unit: ms) |
| axisFormat | String, Function | false | false | `HH` | It is the label value display format of the date type |

### Props by chart
Preparing...

### Props by widget
preparing...


## Events

| Outside axis | Inside axis | Drawing object | Description |
| ---------------- | -------------- | -------------- | ----------- |
| outside#click | inside#click | click | |
| outside#dblclick | inside#dblclick | dblclick | |
| outside#rclick | inside#rclick | rclick | |
| outside#mouseover | inside#mouseover | mouseover | |
| outside#mouseout | inside#mouseout | mouseout | |
| outside#mousemove | inside#mousemove | mousemove | |
| outside#mousedown | inside#mousedown | mousedown | |
| outside#mouseup | inside#mouseup | mouseup | |
