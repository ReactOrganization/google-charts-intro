# How to use Google charts with react

### Installation

```
npm install react-google-charts
```

import it to the component you going to use

```
import { Chart } from "react-google-charts";
```

```
import React from "react";
import ReactDOM from "react-dom";
import Chart from "react-google-charts";

# H2 IMPORTANT! - data is a table and it is gives you a structure of your chart.<br />
First row is a head of your "table" and it is optional.
You can use curly braces to customize your columns for example: { role: "style" }

const data = [
  ["Element", "Density", { role: "style" }],
  ["Copper", 8.94, "#b87333"], // RGB value
  ["Silver", 10.49, "silver"], // English color name

  ["Platinum", 21.45, "color: #e5e4e2"] // CSS-style declaration
];

class App extends React.Component {
  render() {
    return (
      <div className="App">
        <Chart
          chartType="ColumnChart"
          width="100%"
          height="400px"
          data={data}
        />
      </div>
    );
  }
}

const rootElement = document.getElementById("root");
ReactDOM.render(<App />, rootElement);
```

### customization goes in options

      const options = {'title':'How Much Pizza I Ate Last Night',
                     'width':400,
                     'height':300};

##### Then options would go inside of the component

```
class App extends React.Component {
  render() {
    return (
      <div className="App">
        <Chart
          chartType="ColumnChart"
          width="100%"
          height="400px"
          data={data}
          options={options}
        />
      </div>
    );
  }
}
```
# Googel charts vs react-google-chart

Google charts
```
 var data = google.visualization.arrayToDataTable([
   ['Element', 'Density', { role: 'style' }],
   ['Copper', 8.94, '#b87333'],            // RGB value
   ['Silver', 10.49, 'silver'],            // English color name
   ['Gold', 19.30, 'gold'],

 ['Platinum', 21.45, 'color: #e5e4e2' ], // CSS-style declaration
]);
 ```

 react-google-charts
 ```
const data = [
  ["Element", "Density", { role: "style" }],
  ["Copper", 8.94, "#b87333"], // RGB value
  ["Silver", 10.49, "silver"], // English color name
  ["Gold", 19.3, "gold"],
  ["Platinum", 21.45, "color: #e5e4e2"] // CSS-style declaration
];
```
## similarity

Google charts
```
var options = {'title':'How Much Pizza I Ate Last Night',
               'width':400,
               'height':300};
```

react-google-charts
```
const options = {'title':'How Much Pizza I Ate Last Night',
               'width':400,
               'height':300};
```
