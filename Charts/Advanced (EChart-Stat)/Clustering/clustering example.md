
```sqlseal
TABLE clustering = file(./Clustering Data.csv)
MARKDOWN
SELECT * FROM clustering
```

```sqlseal
TABLE clustering = file(./Clustering Data.csv)
ADVANCED MODE
CHART

const datasetArray = data.map(d => ([d.x, d.y]))

var CLUSTER_COUNT = 6;
var DIENSIION_CLUSTER_INDEX = 2;
var COLOR_ALL = [
  '#37A2DA',
  '#e06343',
  '#37a354',
  '#b55dba',
  '#b5bd48',
  '#8378EA',
  '#96BFFF'
];
var pieces = [];
for (var i = 0; i < CLUSTER_COUNT; i++) {
  pieces.push({
    value: i,
    label: 'cluster ' + i,
    color: COLOR_ALL[i]
  });
}
return {
  dataset: [
  {
      source: datasetArray,
      id: 'data'
    },
    {
      transform: {
        type: 'ecStat:clustering',
        print: true,
        config: {
          clusterCount: CLUSTER_COUNT,
          outputType: 'single',
          outputClusterIndexDimension: DIENSIION_CLUSTER_INDEX
        }
      }
    }
  ],
  tooltip: {
    position: 'top'
  },
  visualMap: {
    type: 'piecewise',
    top: 'middle',
    min: 0,
    max: CLUSTER_COUNT,
    left: 10,
    splitNumber: CLUSTER_COUNT,
    dimension: DIENSIION_CLUSTER_INDEX,
    pieces: pieces
  },
  grid: {
    left: 120
  },
  xAxis: {},
  yAxis: {},
  series: {
    type: 'scatter',
    encode: { tooltip: [0, 1] },
    symbolSize: 15,
    itemStyle: {
      borderColor: '#555'
    },
    datasetIndex: 1
  }
};

SELECT * FROM clustering
```
