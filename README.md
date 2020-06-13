# MIMICS: A Large-Scale Data Collection for Search Clarification
Asking a clarification has also been recognized as a major component in conversational information seeking systems. MIMICS is a collection of search clarification datasets for real search queries sampled from the Bing query logs. Each clarification in MIMICS consists of a clarifying question and up to five candidate answers. Here is an example:

| <!-- -->                            | <!-- -->                                                  |
|-------------------------------------|-----------------------------------------------------------|
| query                               | headaches                                                 |
| question                            | What do you want to know about this medical condition?    |
| candidate answers (options)         | symptom, treatment, causes, diagnosis, diet               |


MIMICS contains three datasets: 
  + **MIMICS-Click** includes over 400k unique queries, their associated clarification panes, and the corresponding aggregated user interaction signals (i.e., clicks). 
  + **MIMICS-ClickExplore** is an exploration data that includes aggregated user interaction signals for over 60k unique queries, each with multiple clarification panes. 
  + **MIMICS-Manual** includes over 2k unique real search queries. Each query-clarification pair in this dataset has been manually labeled by at least three trained annotators. It contains graded quality labels for the clarifying question, the candidate answer set, and the landing result page for each candidate answer. 

MIMICS enables researchers to study a number of tasks related to search clarification, including clarification generation and selection, user engagement prediction for clarification, click models for clarification, and analyzing user interactions with search clarification. For more information, refer to the following paper:

- Hamed Zamani, Gord Lueck, Everest Chen, Rodolfo Quispe, Flint Luu, and Nick Craswell. **"MIMICS: A Large-Scale Data Collection for Search Clarification"**, 2020.

For more information of clarification generation and user interactions with clarification, refer to the following artciles:
  - Hamed Zamani, Susan T. Dumais, Nick Craswell, Paul N. Bennett, and Gord Lueck. **"Generating Clarifying Questions for Information Retrieval"**. In Proceedings of the Web Conference, 2020 (WWW '20). [Link](https://dl.acm.org/doi/abs/10.1145/3366423.3380126)
  - Hamed Zamani, Bhaskar Mitra, Everest Chen, Gord Lueck, Fernando Diaz, Paul N. Bennett, Nick Craswell, and Susan T. Dumais. **"Analyzing and Learning from User Interactions for Search Clarification"**. In Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval, 2020 (SIGIR ’20). [Link](https://www.microsoft.com/en-us/research/uploads/prod/2020/05/SIGIR_2020___Analyzing_Clarification_in_Web_Search.pdf)




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
| option_label_1, ..., option_label_5 | (integer) The conditional click probability on each candidate answer. |


## Citation
If you found MIMICS useful, you can cite the following article:
```
Hamed Zamani, Gord Lueck, Everest Chen, Rodolfo Quispe, Flint Luu, and Nick Craswell. "MIMICS: A Large-Scale Data Collection for Search Clarification", arXiv preprint, 2020.
```

bibtex:
```
@article{mimics,
  title={MIMICS: A Large-Scale Data Collection for Search Clarification},
  author={Zamani, Hamed and Lueck, Gord and Chen, Everest and Quispe, Rodolfo and Luu, Flint and Craswell, Nick},
  journal={arXiv preprint arXiv:XXX},
  year={2020},
}
```

## License
Macaw is distributed under the **MIT License**. See the `LICENSE` file for more information.


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
