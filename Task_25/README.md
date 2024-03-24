README.md
# TASK 25 - Textual Entailment
- Homepage: https://www.evalita.it/campaigns/evalita-2009/tasks/textual-entailment/
- Data: http://art.uniroma2.it/zanzotto/resources/RTE-It_2009.zip

## Data
A pair of texts consists of T (for text) and H (hypothesis). 
Textual entailment is defined as a directional relationship between such pairs. 
Systems have to decide whether T entails H, which is the case when the meaning of H can be inferred from T within the context induced by T.

Another way of thinking about this is whether H contains any new information with respect to T: if it doesn’t, H is entailed by T. The hypothesis must be fully entailed by the text. 

When the inference is very probable (but not completely certain) the entailment relation still holds (i.e., in cases where T is true, H is ’most likely’ true as well).

Please do note that the only available options, for this dataset, are ENTAILED and NOT ENTAILED.
**Refer to the .pdf in the folder for further details.**

The dataset is already split into training and test set.

## Expected output

The expected output is two (2) datasets per tasks (train and test splits) + one (1) prompt file per tasks.

Files to submit: 
- `textual_entailment-task1-train-data.jsonl`
- `textual_entailment-task1-test-data.jsonl`
- `textual_entailment-task1-prompt.jsonl`

Each line in the data files should be a JSON object following this format:
```JSON
{
    "id":           int,
    "text":         str,
    "hypothesis":   str,
    "choices":      list[str],
    "label":        int
}
```
In the prompt file you have to report the prompts you designed for the task.
Each line in the prompt files should be a JSON object following this format (max 5 lines):
```JSON
{
    "prompt": str
}
```
