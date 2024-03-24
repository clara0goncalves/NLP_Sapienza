README.md
# TASK 28 - PreTENS
Homepage: https://sites.google.com/view/semeval2022-pretens
GitHub: https://github.com/shammur/SemEval2022Task3?tab=readme-ov-file

## Data
PreTENS is articulated into the two following sub-tasks:
1. a **binary classification sub-task**, which consists in predicting the acceptability label assigned to each sentence of the test set;
2. a **regression sub-task**, which consists in predicting the average score assigned by human annotators on a seven point Likert-scale with respect to the subset of data evaluated via crowdsourcing.

**NOTE**: regarding task 2, the scores (i.e., the mean of the seven-point Likert-scale) are not integers.
It's up to you to cast them to integers, choosing how and motivating your decision, so that you can use them in the prompts.
Basically, you have to reframe a regression task as a classification task, for example adopting the same language descriptors used in Likert scales (e.g., "Eccellente" in place of "7").

The dataset is already split into training and test set and you should use only its Italian part.

## Expected output

The expected output is two (2) datasets per tasks (train and test splits) + one (1) prompt file per tasks.

### Task 1
Files to submit: 
- `PreTENS-task1-train-data.jsonl`
- `PreTENS-task1-test-data.jsonl`
- `PreTENS-task1-prompt.jsonl`


Each line in the data files should be a JSON object following this format:
```JSON
{
    "id":       int,
    "text":     str,
    "choices":  list[str],
    "label":    int
}
```
In the prompt file you have to report the prompts you designed for the task.
Each line in the prompt files should be a JSON object following this format (max 5 lines):
```JSON
{
    "prompt": str
}
```

### Task 2
Files to submit: 
- `PreTENS-task2-train-data.jsonl`
- `PreTENS-task2-test-data.jsonl`
- `PreTENS-task2-train-prompts.jsonl`
- `PreTENS-task2-test-prompts.jsonl`

Each line in the files should be a JSON object following this format:
```JSON
{
    "id":       int,
    "text":     str,
    "choices":  list[str|int],
    "label":    int
}
```
In the prompt file you have to report the prompts you designed for the task.
Each line in the prompt files should be a JSON object following this format (max 5 lines):
```JSON
{
    "prompt": str
}
```
