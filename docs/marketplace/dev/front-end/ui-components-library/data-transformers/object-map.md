---
title: Data Transformer Object-map
description: This document provides details about the Data Transformer Object-map service in the Components Library.
template: concept-topic-template
---


This document provides details about the Data Transformer Object-map service in the Components Library.

## Overview

Data Transformer Object-map is an Angular Service that executes another Data Transformer from the config for specific properties in an object.
In the example below, the `datasource` will return an array with the transformed `date` in every child object.

```ts
<spy-select
  [datasource]="{
    type: 'inline',
    data: [
      {
        type: 'date',
        date: '2020-09-24T15:20:08+02:00',
      },
      {
        type: 'date',
        date: '2020-09-22T15:20:08+02:00',
      },
    ],
    transform: {
      type: 'array-map',
      mapItems: {
        type: 'object-map',
        mapProps: {
          date: {
            type: 'date-parse',
          },
        },
      },
    },
  }"
></spy-select>
```

## Interfaces

`mapProps` - Data Transformer set up with a configuration object.  
`propName` - the name of the property from which the value needs to be transformed.

```ts
export interface ObjectMapDataTransformerConfig extends DataTransformerConfig {
  mapProps: { [propName: string]: DataTransformerConfig };
}

// Service registration
@NgModule({
  imports: [
    DataTransformerModule.withTransformers({
      'object-map': ObjectMapDataTransformerService,
    }),
  ],
})
export class RootModule {}
```