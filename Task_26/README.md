README.md
# TASK 26 - Hypernym Discovery
- Homepage: https://competitions.codalab.org/competitions/17119
- Data: https://drive.google.com/file/d/14_RgB3_it7a_1mLXeRCyzwY5BHdWgnlP/view
## Data
Given a term (concept or entity) as input, the hypernym discovery task consists of retrieving a list with the most appropriate hypernyms from a text corpus.

The **vocabulary file** contains all potential hypernyms for each subtask. 
This is an exhaustive list which contains all hypernyms in the gold data. 
All hypernyms are in their lowercased form.
In this list overgeneric hypernyms such as topic, entity, etc., which are not considered in the gold standard have been filtered, as well as those occurring less than 5 and 3 times on the general-purpose and domain-specific datasets, respectively.

**Data files** contains the list of hyponyms, each line corresponding to a term and its type (Concept or Entity): `hyponym <tab> type`

**Gold files** contain gold standard hypernyms, _each line corresponding to the same line in the corresponding data file_.

Please do note that each hyponym can have a variable number of hypernyms; you should use all hypernyms (in different entries) to create the dataset.
For example, given word x having y, z, u as hypernyms: you will need to produce the entries 
- (x, y, d1, d2, d3)
- (x, z, d1, d2, d3)
- (x, u, d1, d2, d3)
where d1, d2 and d3 are distractors (*be careful to choose unambiguous distractors!*)
You may use the vocabulary file provided, but you have to filter out non-italian words.

The dataset is already split into training and test set and you should use only its Italian part.

## Expected output

The expected output is two (2) datasets per tasks (train and test splits) + one (1) prompt file per tasks.

Files to submit: 
- `hypernym_discovery-task1-train-data.jsonl`
- `hypernym_discovery-task1-test-data.jsonl`
- `hypernym_discovery-task1-prompt.jsonl`

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
