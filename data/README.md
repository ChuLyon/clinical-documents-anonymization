This project requires two disjoint dataset with a specific format.

Of course, these format can be modified according to you needs.

First, the *data-for-trf.json* dataset, which follow the json format:

```{json}
[
    {
        "type.libelle": "doc-type",
        "id": "doc-id",
        "file.contenu": "doc-content"
    },
	{
	},
	...
]
```

Secondly, the *anonymisation-ner.jsonl* dataset, follows the json format:

```{json}
{"id": 0, "tokens": ["list", "of", "tokens", "ner_tags": [0, 0, 0]}
{"id": 1, "tokens": ["another", "list", "of", "tokens", "ner_tags": [0, 0, 0, 0]}
...
```

This second dataset was obtain with [Doccano](https://doccano.herokuapp.com/fr) export format.
