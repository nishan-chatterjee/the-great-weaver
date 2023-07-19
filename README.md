# the-great-weaver
A Graph-based Visualization approach for Related Work Exploration, Claim Detection, Citation Recommendation, and Research Footprint Exploration

Scientific papers are the foundation for expanding understanding, incorporating emerging insights, and building upon existing methodologies. However, the rapid growth of scholarly literature presents challenges in keeping up with the latest developments. Additionally, the process of generating related works sections through extensive literature reviews is time-consuming and resource-intensive. To address these challenges, my research proposal focuses on three interconnected research questions that aim to enhance the efficiency and effectiveness of related works sections in academic papers by combining previously implemented ideas:

Research Question 1: What are the predominant citation types in research papers, and how can they be effectively classified?
> To address this, we can standardize the terminology used in literature reviews, classify citation types by employing chronological or causal organization, and explore unsupervised learning methods for discovering other signals. Academic research graphs such as the ORKG, Microsoft Open Academic Graph, or Connected Papers can be leveraged for classification. The resulting classification signals can then be used to prune the graph-search space and streamline the process of generating contextual candidate options for related works sections.

Research Question 2: How can claims within research papers be automatically detected and contextualized to improve understanding?
> This question focuses on developing methods to automatically identify claims by leveraging relationships between cited research and various sections of papers, such as statements, methodologies, figures, and conclusions. The goal is to enhance the understanding and contextualization of academic claims by providing automated mechanisms for efficient and accurate claim detection and analysis.

Research Question 3: How can related works sections be generated automatically from paper abstracts, and how does this approach compare to previous state-of-the-art methods?
> A multi-step approach can be employed for this question. Firstly, building upon the findings from Research Question 2, claims need to be extracted from papers, linking them to cited papers, and establishing connections. This recursive process generates a contextually aware graph. To enhance contextual understanding, trainable parameter scores are assigned to capture connection strengths. 

> Next, a model can be trained using related works to predict the citations that occur in the related work sections and determine their order. This training involves leveraging the connected graph with the updated edge weights and associated signals generated from the findings of Research Question 1, to provide a comprehensive understanding of the citation patterns. The model can be trained not only with related works from accepted papers but also from rejected and modified accepted papers, incorporating additional signals and time-series perspectives. Furthermore, to automatically generate complete coherent sentences around these related work papers, the coherence and structure of sentences within the related works section need to be analyzed. This would involve employing a large language model to assess the syntactic and semantic connections between sentences. Finally, a joint graph+LLM model could be developed to automatically generate the related works section. This model combines the information from the updated interconnected graph based on automatic claim detection, the trained model for citation prediction, and sentence coherence analysis. By integrating these components, the joint model can effectively generate contextually relevant and well-structured related works sections.

```
Identify claims in papers:
Paper 1        Paper 2       Paper 3
Claim 1        Claim 1       Claim 1
Claim 2        Claim 2       Claim 2
Claim 3        Claim 3       Claim 3

Identify claims and link them from source paper to cited papers:
Claim 1 -----> Paper 2, Paper 3
Claim 2 -----> Paper 1, Paper 3
Claim 3 -----> Paper 1, Paper 2

Perform the same claim detection and linkage recursively to generate a new graph that is contextually more aware of these linkages using trainable parameter scores:
Claim 1 -----> Paper 2, Paper 3
  ├─────────> Claim 2
  └─────────> Claim 3
Claim 2 -----> Paper 1, Paper 3
  ├─────────> Claim 1
  └─────────> Claim 3
Claim 3 -----> Paper 1, Paper 2
  ├─────────> Claim 1
  └─────────> Claim 2

Train a model using related works to predict citations and their order:
Model Trained with Related Works

Analyze how sentences are structured and connect coherently with each other (e.g., using LLM like llamav2):

Generated Sentences and Coherence Analysis

Generate a joint graph+LLM model that can generate related works sections:
Joint Graph+LLM Model

Compare with existing work:
Evaluation and Comparison with State-of-the-Art Methods
```

