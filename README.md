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

- Hamed Zamani, Gord Lueck, Everest Chen, Rodolfo Quispe, Flint Luu, and Nick Craswell. [**"MIMICS: A Large-Scale Data Collection for Search Clarification"**](https://arxiv.org/pdf/2006.10174.pdf), In Proceedings of the 29th ACM International on Conference on Information and Knowledge Management, 2020 (CIKM '20).

For more information of clarification generation and user interactions with clarification, refer to the following artciles:
  - Hamed Zamani, Susan T. Dumais, Nick Craswell, Paul N. Bennett, and Gord Lueck. [**"Generating Clarifying Questions for Information Retrieval"**](https://dl.acm.org/doi/abs/10.1145/3366423.3380126). In Proceedings of the Web Conference, 2020 (WWW '20). 
  - Hamed Zamani, Bhaskar Mitra, Everest Chen, Gord Lueck, Fernando Diaz, Paul N. Bennett, Nick Craswell, and Susan T. Dumais. [**"Analyzing and Learning from User Interactions for Search Clarification"**](https://arxiv.org/pdf/2006.00166.pdf). In Proceedings of the 43rd International ACM SIGIR Conference on Research and Development in Information Retrieval, 2020 (SIGIR ’20). 




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


### The Bing API's Search Results for MIMICS Queries
To enable researchers to use the web search result page (SERP) information, we have also released the search results returned by the Bing's Web Search API for all the queries in the MIMICS datasets. The SERP  data can be downloaded from [here](http://ciir.cs.umass.edu/downloads/mimics-serp/MIMICS-BingAPI-results.zip) (3.2GB compressed, 16GB decompressed). Each line in the file can be loaded as a JSON object and contain all information returned by the Bing's Web Search API.


## Citation
If you found MIMICS useful, you can cite the following article:
```
Hamed Zamani, Gord Lueck, Everest Chen, Rodolfo Quispe, Flint Luu, and Nick Craswell. "MIMICS: A Large-Scale Data Collection for Search Clarification", In Proc. of CIKM 2020.
```

bibtex:
```
@inproceedings{mimics,
  title={MIMICS: A Large-Scale Data Collection for Search Clarification},
  author={Zamani, Hamed and Lueck, Gord and Chen, Everest and Quispe, Rodolfo and Luu, Flint and Craswell, Nick},
  booktitle = {Proceedings of the 29th ACM International on Conference on Information and Knowledge Management},
  series = {CIKM '20},
  year={2020},
}
```

## License
MIMICS is distributed under the **MIT License**. See the `LICENSE` file for more information.


## Terms and Conditions
The ORCAS datasets are intended for non-commercial research purposes only to promote advancement in the field of information retrieval and related areas, and is made available free of charge without extending any license or other intellectual property rights. The dataset is provided "as is" without warranty and usage of the data has risks since we may not own the underlying rights in the documents. We are not be liable for any damages related to use of the dataset. Feedback is voluntarily given and can be used as we see fit. By using any of these datasets you are automatically agreeing to abide by these terms and conditions. Upon violation of any of these terms, your rights to use the dataset will end automatically. If you have questions about use of the dataset or any research outputs in your products or services, we encourage you to undertake your own independent legal review. For other questions, please feel free to contact us at hazamani@microsoft.com.


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
