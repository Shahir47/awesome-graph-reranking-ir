# Awesome Graph Reranking in Information Retrieval [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
Graph-based methods for reordering retrieved documents across information retrieval, question answering, and retrieval-augmented generation.

## Contents
- [Question Answering](#question-answering)
- [General Information Retrieval](#general-information-retrieval)
- [Retrieval-Augmented Generation](#retrieval-augmented-generation)
- [Auxiliary and Specialized Tasks](#auxiliary-and-specialized-tasks)
- [Datasets](#-datasets)
- [Learning Paradigms](#-learning-paradigms)

## 🔥 NEWS
* 07.27.2026: Release of **V2** of the survey on [arXiv](https://arxiv.org/abs/2503.14802)
* 03.19.2025: Release of **V1** of the survey on [arXiv](https://arxiv.org/abs/2503.14802v1)

## 🚀 Related Work from Our Group
[Density2R](https://ieeexplore.ieee.org/document/11401587), an efficient zero-shot document re-ranking method for information retrieval, RAG, and LLM-based reranking, published at IEEE BigData 2025.
> It is a lightweight zero-shot document re-ranking method that uses embedding density over LLM parametric knowledge to reduce token cost and latency for RAG and information retrieval pipelines.

🔗 GitHub: [Density2R_GitHub](https://github.com/Shahir47/Density2R)

## 🔍 OVERVIEW
`V2` The two-stage information retrieval (IR) framework, also known as the retrieve-then-re-rank pipeline, has empowered numerous AI paradigms, including retrieval-augmented generation (RAG) and question-answering (QA) systems that leverage ad hoc knowledge to address the rapidly expanding information landscape. In this setting, graph structures have emerged as a promising mechanism for context augmentation, further enhancing re-ranking frameworks through structured relational modeling, semantic dependency representation, and adaptive retrieval strategies. Consequently, graph representation learning techniques have been actively explored alongside leading IR paradigms. Despite increased research interest in graph-based re-ranking methods, a comprehensive study that connects existing approaches and provides a clear overview of this paradigm remains absent. In this survey, we provide an in-depth review of graph-based re-ranking models, tracing their history, evolution, and state-of-the-art development. To facilitate a clear understanding of this paradigm, we introduce an intuitive taxonomy that organizes graph-based re-ranking models by application domain and methodological characteristics. We also present a chronological timeline that illustrates the evolution of graph-based re-ranking methods. In addition, we analyze the experimental setups of representative studies and provide detailed insight into their findings. We conclude by providing recommendations on future research based on community-wide challenges and opportunities.

## 🌳 TAXONOMY
This taxonomy organizes graph-based re-ranking methods into four application areas: General Information Retrieval, Question Answering, Retrieval-Augmented Generation, and Auxiliary and Specialized Tasks. General IR is further categorized by methodology, including heuristic and centrality-based methods, adaptive corpus-graph traversal, entity-centric approaches, domain-specific methods, and other specialized graph designs. QA methods are grouped by task setting: open-domain, knowledge-graph, temporal knowledge-graph, and multi-hop question answering. The auxiliary category covers related tasks such as answer sentence selection, semantic parsing, entity re-ranking, and term re-ranking. This structure provides a clear overview of how graph-based techniques map to different re-ranking problems.
![Taxonomy](./assets/taxonomy.png)

## 🧭 TIMELINE
The timeline illustrates the evolution of graph-based re-ranking from 2008 to the present across the four taxonomy categories. Its spacing reflects publication density, giving greater emphasis to the field’s rapid recent growth. Early work focused on general IR, using similarity graphs and centrality measures such as PageRank to rescore documents. During the 2010s, researchers increasingly incorporated entities, knowledge graphs, and neural ranking models, while graph-based re-ranking expanded into question answering. More recent work emphasizes adaptive candidate expansion through corpus graphs, integration with pretrained and large language models, and emerging applications in RAG pipelines.
![Timeline](./assets/timeline.png)

## Question-Answering
Graph-based re-ranking in QA selects the passages, facts, triples, or evidence paths most useful for producing an answer. Graphs help connect related pieces of evidence, remove irrelevant knowledge, preserve temporal consistency, and support reasoning across multiple documents. The category covers open-domain QA, knowledge-graph QA, temporal knowledge-graph QA, and multi-hop QA, each of which uses a different form of graph structure to organize and prioritize evidence.

| Model | Paper | Venue | Date | Resources |
|---|---|---|---|---|
|KG-FiD|[KG-FiD: Infusing Knowledge Graph in Fusion-in-Decoder for Open-Domain Question Answering](https://aclanthology.org/2022.acl-long.340/)|ACL|2022||
||[Efficient and Accurate Contextual Re-Ranking for Knowledge Graph Question Answering](https://aclanthology.org/2024.lrec-main.496/)|LREC-COLING|2024||
|Q-KGR|[Question-guided Knowledge Graph Re-scoring and Injection for Knowledge Graph Question Answering](https://aclanthology.org/2024.findings-emnlp.524/)|ACL|2024|[GitHub](https://github.com/EchoDreamer/Q-KGR)|
|TimeR4|[TimeR4 : Time-aware Retrieval-Augmented Large Language Models for Temporal Knowledge Graph Question Answering](https://aclanthology.org/2024.emnlp-main.394/)|ACL|2024|[GitHub](https://github.com/qianxinying/TimeR4)|
||[Learning to Retrieve Reasoning Paths over Wikipedia Graph for Question Answering](https://arxiv.org/abs/1911.10470)|ICLR|2019|[GitHub](https://github.com/AkariAsai/learning_to_retrieve_reasoning_paths)|
|IDRQA|[Answering Any-hop Open-domain Questions with Iterative Document Reranking](https://arxiv.org/abs/2009.07465)|SIGIR|2021||

## General Information Retrieval
This category covers graph-based methods for improving the ranking of documents or passages in conventional search systems. These approaches use graph signals in several ways: applying centrality-based algorithms, exploring corpus graphs to recover relevant documents missed by the initial retriever, enriching representations with knowledge-graph entities, and modeling relationships among candidates. It includes traditional and heuristic models, adaptive re-ranking, entity-centric methods, domain-specific approaches, and other specialized graph designs.

| Model | Paper | Venue | Date | Resources |
|---|---|---|---|---|
||[Re-Ranking Search Results Using Document-Passage Graphs](https://dl.acm.org/doi/10.1145/1390334.1390539)|SIGIR|2008||
|GBRM|[Effective Latent Space Graph-based Re-ranking Model with Global Consistency](https://dl.acm.org/doi/10.1145/1498759.1498791)|WSDM|2009||
|PsgAidRank|[Utilizing Inter-Passage and Inter-Document Similarities for Reranking Search Results](https://dl.acm.org/doi/10.1145/1877766.1877769)|TOIS|2010||
||[PageRank without Hyperlinks: Structural Reranking using Links Induced by Language Models](https://dl.acm.org/doi/10.1145/1852102.1852104)|TOIS|2010||
|TRM & TDM|[Information Retrieval by Document Re-ranking using Term Association Graph](https://dl.acm.org/doi/10.1145/2660859.2660927)|ICONIAAC|2014||
|EsdRank|[EsdRank: Connecting Query and Documents through External Semi-Structured Data](https://dl.acm.org/doi/10.1145/2806416.2806456)|CIKM|2015||
|GAR|[Adaptive Re-Ranking with a Corpus Graph](https://dl.acm.org/doi/10.1145/3511808.3557231)|CIKM|2022|[GitHub](https://github.com/terrierteam/pyterrier_adaptive/tree/main)|
|QDG|[Effective Adhoc Retrieval through Traversal of a Query-Document Graph](https://link.springer.com/chapter/10.1007/978-3-031-56063-7_6)|ECIR|2024||
||[Adaptive Re-Ranking as an Information-Seeking Agent](https://ceur-ws.org/Vol-3318/paper9.pdf)|CEUR Workshop|2022||
||[Fairness-Aware Exposure Allocation via Adaptive Reranking](https://dl.acm.org/doi/10.1145/3626772.3657794)|SIGIR|2024||
|SlideGAR|[Guiding Retrieval using LLM-based Listwise Ranker](https://link.springer.com/chapter/10.1007/978-3-031-88708-6_15)|ECIR|2025|[GitHub](https://github.com/Mandeep-Rathee/llmgar)|
|Quam|[Quam: Adaptive Retrieval through Query Affinity Modelling](https://dl.acm.org/doi/10.1145/3701551.3703584)|WSDM|2025|[GitHub](https://github.com/Mandeep-Rathee/quam)|
|ORE|[Breaking the Lens of the Telescope: Online Relevance Estimation over Large Retrieval Sets](https://dl.acm.org/doi/10.1145/3726302.3729910)|SIGIR|2025|[GitHub](https://github.com/elixir-research-group/ORE)|
|LADR|[Lexically-Accelerated Dense Retrieval](https://dl.acm.org/doi/abs/10.1145/3539618.3591715)|SIGIR|2023|[GitHub](https://github.com/Georgetown-IR-Lab/ladr)|
||[Bag-of-Entities Representation for Ranking](https://dl.acm.org/doi/10.1145/2970398.2970423)|ICTIR|2016||
|AttR-Duet|[Word-Entity Duet Representations for Document Ranking](https://dl.acm.org/doi/10.1145/3077136.3080768)|SIGIR|2017||
|EDRM|[Entity-Duet Neural Ranking: Understanding the Role of Knowledge Graph Semantics in Neural Information Retrieval](https://aclanthology.org/P18-1223/)|ACL|2018|[GitHub](https://github.com/thunlp/EntityDuetNeuralRanking)|
|GAT-reRanker|[Document reRanking using GAT-Cross Encoder](https://papers.dice-research.org/2024/KIAM-Reranking/public.pdf)||||
|KGPR|[KGPR: Knowledge Graph Enhanced Passage Ranking](https://dl.acm.org/doi/10.1145/3583780.3615252)|CIKM|2023|[GitHub](https://github.com/jyfang6/KGPR)|
|KERM|[Incorporating Explicit Knowledge in Pre-trained Language Models for Passage Re-ranking](https://dl.acm.org/doi/10.1145/3477495.3531997)|SIGIR|2022|[GitHub](https://github.com/CSQianDong/KERM)|
|QDER|[QDER: Query-Specific Document and Entity Representations for Multi-Vector Document Re-Ranking](https://dl.acm.org/doi/10.1145/3726302.3730065)|SIGIR|2025|[GitHub](https://github.com/shubham526/SIGIR2025-QDER)|
|DREQ|[DREQ: Document Re-ranking Using Entity-Based Query Understanding](https://link.springer.com/chapter/10.1007/978-3-031-56027-9_13)|ECIR|2024|[GitHub](https://github.com/shubham526/ECIR2024-DREQ)|
|GraphMonoT5|[Empowering Language Model with Guided Knowledge Fusion for Biomedical Document Re-ranking](https://link.springer.com/chapter/10.1007/978-3-031-66538-7_25)|AIME|2024||
|GRAPH-JPDRMM|[AUEB-NLPatBioASQ8: Biomedical Document and Snippet Retrieval](https://ceur-ws.org/Vol-2696/paper_122.pdf)|CLEF|2020||
|KEGNR|[Knowledge enhanced edge-driven graph neural ranking for biomedical information retrieval](https://www.sciencedirect.com/science/article/abs/pii/S095741742402654X)|Expert Systems with Applications|2025||
|KG-Rank|[KG-Rank: Enhancing Large Language Models for Medical QA with Knowledge Graphs and Ranking Techniques](https://aclanthology.org/2024.bionlp-1.13/)|ACL|2024|[GitHub](https://github.com/ruiyang-medinfo/KG-Rank)|
||[Matching, Re-ranking and Scoring: Learning Textual Similarity by Incorporating Dependency Graph Alignment and Coverage Features](https://link.springer.com/chapter/10.1007/978-3-319-77113-7_30)|CICLING|2017||
|PassageRank|[Faster BERT-based re-ranking through Candidate Passage Extraction](https://trec.nist.gov/pubs/trec29/papers/UoB.DL.pdf)|TREC|2020|[GitHub](https://github.com/kylereed96/trec-dl-2020)|
||[A Graph-based Approach at Passage Level to Investigate the Cohesiveness of Documents](https://doi.org/10.5220/0010619101150123)|DATA|2021||
|GRMM|[A Graph-based Relevance Matching Model for Ad-hoc Retrieval](https://ojs.aaai.org/index.php/AAAI/article/view/16599)|AAAI|2021|[GitHub](https://github.com/CRIPAC-DIG/GRMM)|
|LGRe|[Latent graph recurrent network for document ranking](https://link.springer.com/chapter/10.1007/978-3-030-73197-7_6)|DASFAA|2021|[GitHub](https://github.com/CSQianDong/LGRe)|
|DGRe|[Disentangled graph recurrent network for document ranking](https://link.springer.com/article/10.1007/s41019-022-00179-3)|Data Science & Engineering|2022|[GitHub](https://github.com/DQ0408/DGRe)|
|PGT|[PGT: Pseudo Relevance Feedback Using a Graph-Based Transformer](https://link.springer.com/chapter/10.1007/978-3-030-72240-1_46)|ECIR|2021||
|GNRR|[Graph Neural Re-Ranking via Corpus Graph](https://arxiv.org/abs/2406.11720)|ArXiv|2024||
|MiM & LiM|[Passage Retrieval on Structured Documents using Graph Attention Networks](https://link.springer.com/chapter/10.1007/978-3-030-99739-7_2)|CLEF-IP|2022||
||[Sparse Pairwise Re-ranking with Pre-trained Transformers](https://dl.acm.org/doi/10.1145/3539813.3545140)|SIGIR|2022|[GitHub](https://github.com/webis-de/ICTIR-22)|
|PRP-Graph|[PRP-Graph: Pairwise Ranking Prompting to LLMs with Graph Aggregation for Effective Text Re-ranking](https://aclanthology.org/2024.acl-long.313/)|ACL|2024|[GitHub](https://github.com/Memelank/PRP-Graph)|

## Retrieval-Augmented Generation
In RAG, graph-based re-ranking filters retrieved evidence before it is supplied to a language model, helping ground generation in more relevant and reliable information. Methods may construct graphs over documents, passages, entities, or semantic representations to capture relationships that independent relevance scoring can overlook. Graph neural networks, semantic graphs, and diffusion-based ranking can then promote mutually supporting evidence while suppressing noisy or redundant context.

| Model | Paper | Venue | Date | Resources |
|---|---|---|---|---|
|G-RAG|[Don't Forget to Connect! Improving RAG with Graph-based Reranking](https://arxiv.org/abs/2405.18414)|Preprint|2024||
|QUASAR|[RAG-based Question Answering over Heterogeneous Data and Text](https://arxiv.org/abs/2412.07420)|Preprint|2024|[GitHub](https://github.com/PhilippChr/QUASAR)|
|Diffusion-Aided RAG|[Diffusion-Aided RAG: Elevating Dense-Retrieval Chatbots via Graph-Based Diffusion Reranking](https://aclanthology.org/2025.clicit-1.36/)|CLiC|2025|[GitHub](https://github.com/sai0499/Diffusion-Page-Reranking-aided-Dense-Retrieval-for-RAG-)|

## Auxiliary and Specialized Tasks
This category extends graph-based re-ranking beyond full documents and passages to more specialized candidate types. It includes answer sentence selection, where individual answer candidates are ranked; semantic parsing, where candidate logical forms are evaluated using their structural relationships; entity re-ranking, where entities are prioritized using graph connections and textual context; and term re-ranking, where domain-relevant terms are identified through graph-based importance signals.

| Model | Paper | Venue | Date | Resources |
|---|---|---|---|---|
|EQAG-GNN|[Question-Answer Sentence Graph for Joint Modeling Answer Selection](https://aclanthology.org/2023.eacl-main.68/)|EACL|2023||
|MPGE|[Capturing Sentence Relations for Answer Sentence Selection with Multi-Perspective Graph Encoding](https://ojs.aaai.org/index.php/AAAI/article/view/6436)|AAAI|2020||
|CASSIE|[Question-Context Alignment and Answer-Context Dependencies for Effective Answer Sentence Selection](https://www.isca-archive.org/interspeech_2023/nguyen23b_interspeech.html)|INTERSPEECH|2023||
|GTCV|[Graph-Based Transformer with Cross-Candidate Verification for Semantic Parsing](https://ojs.aaai.org/index.php/AAAI/article/view/6408)|AAAI|2020||
|ENT Rank|[ENT Rank: Retrieving entities for topical information needs through entity-neighbor-text relations](https://dl.acm.org/doi/10.1145/3331184.3331257)|SIGIR|2019|[GitHub](https://github.com/TREMA-UNH/ENT-rank)|
|Term Ranker|[Term Ranker: A Graph-Based Re-Ranking Approach](https://aaai.org/papers/310-flairs-2016-12917/)|AAAI|2016||

## 📊 DATASETS
The datasets used to evaluate graph-based re-ranking across IR, QA, RAG, and specialized tasks, providing a quick overview of the benchmark resources adopted by different studies.

| Dataset | #Corpus | #Queries | Relevance Level | Usage |
|---|---|---|---|---|
|[MSMARCO Passage Ranking](https://microsoft.github.io/msmarco/Datasets)|8.8M|809k|Binary|Train|
|[MSMARCO Passage Ranking v2](https://microsoft.github.io/msmarco/Datasets)|138M|277K|Binary|Train|
|[MSMARCO Dev (small)](https://microsoft.github.io/msmarco/Datasets)|8.8M|6,980|Binary|Test|
|[TREC DL19 (judged)](https://trec.nist.gov/data/deep2019.html)|8.8M|43|4-level|Test|
|[TREC DL20 (judged)](https://trec.nist.gov/data/deep2020.html)|8.8M|54|4-level|Test|
|[TREC DL21 (judged)](https://trec.nist.gov/data/deep2021.html)|138M|53|4-level|Test|
|[TREC DL22 (judged)](https://trec.nist.gov/data/deep2022.html)|138M|76|4-level|Test|
|[TREC DL Hard](https://ir-datasets.com/trec-dl-hard.html)|8.8M|50|4-level|Test|
|[TREC Robust04](https://trec.nist.gov/data/robust/04.guidelines.html)|528K|250|3-level|Test|
|[TREC News 2021](https://trec.nist.gov/data/news2021.html)|728,626|51|5-level|Test|
|[TREC CORE 2018](https://github.com/trec-core/2018)|595K|50|3-level|Test|
|[TREC COVID](https://ir.nist.gov/covidSubmit/index.html)|171,332|50|3-level|Test|
|[CODEC](https://github.com/grill-lab/CODEC)|729,824|42|4-level|Test|
|[Ohsumed](https://ir-datasets.com/ohsumed.html)|348,566|106|3-level|Test|
|[ClueWeb09](https://lemurproject.org/clueweb09/)|1B|200|3-level/6-level|Test|
|[ClueWeb12](https://lemurproject.org/clueweb12/)|733M|100|6-level|Test|
|[TREC8](https://ir-datasets.com/disks45.html)|528K|50|Binary|Test|
|TREC AP|242,918|99|Binary|-|
|TREC WSJ|173,252|50|Binary|-|

## 🎓 LEARNING PARADIGMS
The learning paradigms used to develop graph-based re-rankers include supervised learning, ad-hoc methods, supervised fine-tuning, zero-shot, unsupervised, online, and weakly supervised learning.
![Timeline](./assets/learning_paradigm.png)

## ⭐ CITATION
If you find this work helpful in your research, please consider citing our work.
```
@article{zaoad2025graph,
  title={Graph-based re-ranking: Emerging techniques, limitations, and opportunities},
  author={Zaoad, Md Shahir and Zawad, Niamat and Ranade, Priyanka and Krogman, Richard and Khan, Latifur and Holt, James},
  journal={arXiv preprint arXiv:2503.14802},
  year={2025}
}
```
