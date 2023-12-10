# Bundles Builder

Build bundles from blocks and display the goals tha can be archived based on the blocks selected.

## Data structure

```js
    {
        clients: {
            ['farms']: {
                code: 'client/farms',
                name: 'Farms',
            },
            ['dc']: {
                code: 'client/dc',
                name: 'Distribution Centers',
            },
            ['packing']: {
                code: 'client/packing',
                name: 'Packing',
            },
        },
        goals: {
            ['goal/traceability']: {
                code: 'goal/traceability',
                name: 'Traceability',
                description: 'Description',
                rules: {
                    requires: 2, // two blocks to complete goal
                    byClient: {
                        farm: {
                            requires: 4,
                        },
                    },
                },
            }
        },
        blocks: {
            ['block/code']: {
                code : 'block/code',
                name: 'Block name',
                description: 'Block description',
                variants: ['block/code/variant/red', 'block/code/variant/blue'],
                clients: ['farm', 'dc', 'packing'],
                goals: [],
                price: 10,
            },
            ['block/code/variant/red']: {
                ...
            }
            ['block/code/variant/blue']: {
                ...
            }
            ['block/inventory']: {
                code : 'block/inventory',
                name: 'Inventory',
                description: 'Inventory',
                variants: ['block/code/variant/red',],
                clients: ['farm', 'dc', 'packing'],
                goals: [],
                price: 10,
            },
            ['block/harvest']: {
                code : 'block/harvest',
                name: 'Harvest',
                description: '-',
                variants: ['block/harvest/variant/basic'],
                clients: ['farm'],
                goals: [],
                price: 10,
                dependsOn: ['inventory'],
            },
            ['block/harvest/variant/basic']: {
                code : 'block/harvest/variant/basic',
                name: 'Harvest Basic',
                description: '-',
                variants: ['block/harvest'],
                clients: ['farm'],
                goals: [],
                price: 10,
            },
            ['block/packing']: {
                code : 'block/packing',
                name: 'Packing',
                description: '-',
                variants: ['block/packing/variant/basic'],
                clients: ['farm', 'packing'],
                goals: [],
                price: 10,
                dependsOn: ['inventory'],
            },
            ['block/packing/variant/basic']: {
                code : 'block/packing/variant/basic',
                name: 'PackingB Basic',
                description: '-',
                variants: ['block/packing'],
                clients: ['farm', 'packing'],
                goals: [],
                price: 10,
            },
            ['block/shipping']: {
                code : 'block/shipping',
                name: 'Shipping',
                description: '-',
                variants: ['block/shipping/variant/basic'],
                clients: ['farm', 'packing'],
                goals: [],
                price: 10,
                dependsOn: ['inventory'],
            },
            ['block/shipping/variant/basic']: {
                code : 'block/shipping/variant/basic',
                name: 'Shipping Basic',
                description: '-',
                variants: ['block/shipping/variant/basic'],
                clients: ['farm', 'packing'],
                goals: [],
                price: 10,
            },
        },
        bundles: [
            {
                name: 'Get full traceability',
                questions: {

                },
            }
        ],
    }
```





