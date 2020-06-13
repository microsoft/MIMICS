# MIMICS: A Large-Scale Data Collection for Conversational Search
Asking a clarification has also been recognized as a major component in conversational information seeking systems. MIMICS is a collection of search clarification datasets for real search queries sampled from the Bing query logs. Each clarification in MIMICS consists of a clarifying question and up to five candidate answers. MIMICS contains three datasets: 
  + MIMICS-Click includes over 400k unique queries, their associated clarification panes, and the corresponding aggregated user interaction signals (i.e., clicks). 
  + MIMICS-ClickExplore is an exploration data that includes aggregated user interaction signals for over 60k unique queries, each with multiple clarification panes. 
  + MIMICS-Manual includes over 2k unique real search queries. Each query-clarification pair in this dataset has been manually labeled by at least three trained annotators. It contains graded quality labels for the clarifying question, the candidate answer set, and the landing result page for each candidate answer. 

MIMICS enables researchers to study a number of tasks related to search clarification, including clarification generation and selection, user engagement prediction for clarification, click models for clarification, and analyzing user interactions with search clarification. For more information, refer to the following paper:

- Hamed Zamani, Gord Lueck, Everest Chen, Rodolfo Quispe, Flint Luu, and Nick Craswell. "MIMICS: A Large-Scale Data Collection for Search Clarification".



## Data Format
The datasets are released in a tab-separated file format (TSV), with the header in the first row of each file. The column descriptions are given below. For more detail, refer to the paper mentioned above.

### MIMICS-Click and MIMICS-ClickExplore

| Column(s)                           | Description                                                           |
|-------------------------------------|-----------------------------------------------------------------------|
| query                               | (string) The query text.                                              |
| question                            | (string) The clarifying question.                                     |
| option_1, ..., option_5             | (string) Up to five candidate answers.                                |
| impression_level                    | (string) A three-level impression label (i.e., low, medium, or high). |
| engagement_level                    | (integer) A label in [0, 10] representing total user engagements.     |
| option_cctr_1, ..., option_cctr_5   | (real) The conditional click probability on each candidate answer.    |


### MIMICS-Manual

| Column(s)                           | Description                                                           |
|-------------------------------------|-----------------------------------------------------------------------|
| query                               | (string) The query text.                                              |
| question                            | (string) The clarifying question.                                     |
| option_1, ..., option_5             | (string) Up to five candidate answers.                                |
| question_label                      | (integer) A three-level quality label for the clarifying question     |
| options_overall_label               | (integer) A three-level quality label for the candidate answer set    |
| option_label_1, ..., option_label_5 | (real) The conditional click probability on each candidate answer.    |



## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
