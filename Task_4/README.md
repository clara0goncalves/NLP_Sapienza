**WiC-ITA**

LINK: https://wic-ita.github.io/

For information about the Word-in-Context (WiC) task, check this paper: https://aclanthology.org/N19-1128.pdf

Download the data from https://github.com/wic-ita/data/tree/main/binary
### Reformat data:
Reformat the data following this standard:

```JSON
{ 
  "id": str, 
  "lemma": str, 
  "sentence1": str,
  "sentence2": str,
  "start1": int,
  "end1": int, 
  "start2": int, 
  "end2": int,
  "choices": list[str],
  "label": int
}
```
write the resulting jsons in ```WiC-ITA_{split}.jsonl```, replace {split} with [train, dev, test] according to the data you are processing.


### Prompts

Create ```prompt.jsonl```.
In this file you have to report the prompts you designed for the task. 
Each line in your output file (1 line per prompt) must be a JSON object like the one below:

```JSON
{
    "prompt": "..."
}
```


## Deliver format

You have to format your data using JSON Lines standard.
