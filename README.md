# Awesome Data Valuation

<img src="https://imgur.com/wkCjCds.png" alt="data market problem" width="400"/>

💱 A curated list of data valuation (DV) to design your next data marketplace. DV aims to understand the value of a data point for a given machine learning task and is an essential primitive in the design of data marketplaces and explainable AI.

### Legend
💻 Code available

🎥 Talk / Slides

## Contents

| Table of Contents |
| --- |
| [1. What is your data worth? (DV Algorithms)](#what-is-your-data-worth) |
| &nbsp;&nbsp;&nbsp;&nbsp;[1.1. Shapley Value & Cooperative Game Theory](#shapley-value--cooperative-game-theory) |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.1.1. Efficient algorithms](#efficient-algorithms) |
| &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.1.2. Benchmarks, Criticism & Relaxations](#benchmarks-criticism--relaxations) |
| &nbsp;&nbsp;&nbsp;&nbsp;[1.2. Influence functions & LOO](#influence-functions--loo) |
| &nbsp;&nbsp;&nbsp;&nbsp;[1.3. Reinforcement Learning](#reinforcement-learning) |
| &nbsp;&nbsp;&nbsp;&nbsp;[1.4. Deep Neural Networks](#deep-neural-networks) |
| &nbsp;&nbsp;&nbsp;&nbsp;[1.5. Out-of-Bag score](#out-of-bag-score) |
| [2. Benchmarks](#benchmarks) |
| [3. Libraries](#libraries) |
| &nbsp;&nbsp;&nbsp;&nbsp;[3.1. Surveys](#surveys) |
| [4. Designing data marketplaces](#designing-data-marketplaces) |
| &nbsp;&nbsp;&nbsp;&nbsp;[4.1. Data market system designs](#data-market-system-designs) |
| &nbsp;&nbsp;&nbsp;&nbsp;[4.2. Automatic data compliance](#automatic-data-compliance) |
| &nbsp;&nbsp;&nbsp;&nbsp;[4.3. Data valuation applications](#data-valuation-applications) |
| [5. Data markets and society](#data-markets-and-society) |
| &nbsp;&nbsp;&nbsp;&nbsp;[5.1. Economics of Data](#economics-of-data) |
| &nbsp;&nbsp;&nbsp;&nbsp;[5.2. Data Dignity](#data-dignity) |
| [6. Strategic adaptation](#strategic-adaptation) |
| &nbsp;&nbsp;&nbsp;&nbsp;[6.1. Performative prediction](#performative-prediction) |
| &nbsp;&nbsp;&nbsp;&nbsp;[6.2. Strategic classification](#strategic-classification) |
| [7. Data Valuation Researchers](#data-valuation-researchers) |


## What is your data worth?

### Shapley Value & Cooperative Game Theory

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Towards Efficient Data Valuation Based on the Shapley Value](http://proceedings.mlr.press/v89/jia19a.html) | Ruoxi Jia & David Dao, Boxin Wang, Frances Ann Hubis, Nick Hynes, Nezihe Merve Gürel, Bo Li, Ce Zhang, Dawn Song, Costas J. Spanos | 2019 | <details><summary>Summary</summary> Jia et al. (2019) contribute theoretical and practical results for efficient methods for approximating the Shapley value (SV). They show that methods with a sublinear amount of model evaluations are possible and further reductions can be made for sparse SVs. Lastly, they introduce two practical SV estimation methods for ML tasks, one for uniformly stable learning algorithms and one for smooth loss functions. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{jia2019towards,<br>  title={Towards efficient data valuation based on the shapley value},<br>  author={Jia, Ruoxi and Dao, David and Wang, Boxin and Hubis, Frances Ann and Hynes, Nick and G{\"u}rel, Nezihe Merve and Li, Bo and Zhang, Ce and Song, Dawn and Spanos, Costas J},<br>  booktitle={The 22nd International Conference on Artificial Intelligence and Statistics},<br>  pages={1167--1176},<br>  year={2019},<br>  organization={PMLR}<br>}</pre></details> | [💻](https://github.com/sunblaze-ucb/data-valuation) | |
| [Data Shapley: Equitable Valuation of Data for Machine Learning](http://proceedings.mlr.press/v97/ghorbani19c.html) | Amirata Ghorbani, James Zou | 2019 | <details><summary>Summary</summary> Ghorbani & Zou (2019) introduce (data) Shapley value to equitably measure the value of each training point to a supervised learners performance. They further outline several benefits of the Shapley value, e.g. being able to capture outliers or inform what new data to acquire, as well as develop Monte Carlo and gradient-based methods for its efficient estimation. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{ghorbani2019data,<br>  title={Data shapley: Equitable valuation of data for machine learning},<br>  author={Ghorbani, Amirata and Zou, James},<br>  booktitle={International Conference on Machine Learning},<br>  pages={2242--2251},<br>  year={2019},<br>  organization={PMLR}<br>}</pre></details> | [💻](https://github.com/amiratag/DataShapley) | |
| [A Distributional Framework for Data Valuation](https://arxiv.org/abs/2002.12334) | Amirata Ghorbani, Michael P. Kim, James Zou | 2020 | <details><summary>Summary</summary> Ghorbani et al. (2020) formulate the Shapley value as a distributional quantity in the context of an underlying data distribution instead of a fixed dataset. They further introduce a novel sampling-based algorithm for the distributional Shapley value with strong approximation guarantees. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{ghorbani2020distributional,<br>  title={A Distributional Framework for Data Valuation},<br>  author={Ghorbani, Amirata, P. Kim, Michael and Zou, James},<br>  booktitle={International Conference on Machine Learning},<br>  year={2020}<br>}</pre></details> | [💻](https://github.com/amiratag/DistributionalShapley) | |
| [Asymmetric Shapley values: incorporating causal knowledge into model-agnostic explainability](https://proceedings.neurips.cc//paper/2020/hash/0d770c496aa3da6d2c3f2bd19e7b9d6b-Abstract.html) | Christopher Frye, Colin Rowat, Ilya Feige | 2020 | <details><summary>Summary</summary> Frye et al. (2020) incorporate causality into the Shapley value framework. Importantly, their framework can handle any amount of causal knowledge and does not require the complete causal graph underlying the data. </details> | <details><summary>Bibtex</summary><pre>@article{frye2020asymmetric,<br>  title={Asymmetric Shapley values: incorporating causal knowledge into model-agnostic explainability},<br>  author={Frye, Christopher and Rowat, Colin and Feige, Ilya},<br>  journal={Advances in Neural Information Processing Systems},<br>  volume={33},<br>  year={2020}<br>}</pre></details> | | [🎥](https://www.youtube.com/watch?v=7d13f4UaAn0) |
| [Collaborative Machine Learning with Incentive-Aware Model Rewards](https://arxiv.org/abs/2010.12797) | Rachael Hwee Ling Sim, Yehong Zhang, Mun Choon Chan, Bryan Kian Hsiang Low | 2020 | <details><summary>Summary</summary> Sim et al. (2020) introduce a data valuation method with separate ML models as rewards based on the Shapley value and information gain on model parameters given its data. They further define several conditions for incentives such as Shapley fairness, stability, individual rationality, and group welfare, that are suitable for the freely replicable nature of their model reward scheme. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{sim2020collaborative,<br>  title={Collaborative machine learning with incentive-aware model rewards},<br>  author={Sim, Rachael Hwee Ling and Zhang, Yehong and Chan, Mun Choon and Low, Bryan Kian Hsiang},<br>  booktitle={International Conference on Machine Learning},<br>  pages={8927--8936},<br>  year={2020},<br>  organization={PMLR}<br>}</pre></details> | | |
| [Validation free and replication robust volume-based data valuation](https://proceedings.neurips.cc/paper/2021/hash/59a3adea76fadcb6dd9e54c96fc155d1-Abstract.html) | Xinyi Xu, Zhaoxuan Wu, Chuan Sheng Foo, Bryan Kian Hsiang Low | 2021 | <details><summary>Summary</summary> Xu et al. (2021) propose using data diversity via robust volume for measuring the value of data. This removes the need for a validation set and allows for guarantees on replication robustness but suffers from the curse of dimensionality and may ignore useful information in the validation set. </details> |  <details><summary>Bibtex</summary><pre>@article{xu2021validation,<br>  title={Validation free and replication robust volume-based data valuation},<br>  author={Xu, Xinyi and Wu, Zhaoxuan and Foo, Chuan Sheng and Low, Bryan Kian Hsiang},<br>  journal={Advances in Neural Information Processing Systems},<br>  volume={34},<br>  year={2021}<br>}</pre></details> | [💻](https://github.com/ZhaoxuanWu/VolumeBased-DataValuation) | |
| [Beta Shapley: a Unified and Noise-reduced Data Valuation Framework for Machine Learning](https://arxiv.org/abs/2110.14049) | Yongchan Kwon, James Zou | 2021 | <details><summary>Summary</summary> Kwon & Zou (2022) introduce Beta Shapley, a generalization of Data Shapley by relaxing the efficiency axiom. </details> | <details><summary>Bibtex</summary><pre>@article{kwon2021beta,<br>  title={Beta Shapley: a Unified and Noise-reduced Data Valuation Framework for Machine Learning},<br>  author={Kwon, Yongchan and Zou, James},<br>  journal={arXiv preprint arXiv:2110.14049},<br>  year={2021}<br>}</pre></details> | | |
| [Gradient-Driven Rewards to Guarantee Fairness in Collaborative Machine Learning](https://proceedings.neurips.cc/paper/2021/hash/8682cc30db9c025ecd3fee433f8ab54c-Abstract.html) | Xinyi Xu, Lingjuan Lyu, Xingjun Ma, Chenglin Miao, Chuan Sheng Foo, Bryan Kian Hsiang Low | 2021 | <details><summary>Summary</summary> Xu et al. (2021) propose cosine gradient Shapley value to fairly evaluate the expected contribution of each agent's update in the federated learning setting removing the need for an auxiliary validation dataset. They further introduce a novel training-time gradient reward mechanism with a fairness guarantee. </details> | <details><summary>Bibtex</summary><pre>@article{xu2021gradient,<br>  title={Gradient driven rewards to guarantee fairness in collaborative machine learning},<br>  author={Xu, Xinyi and Lyu, Lingjuan and Ma, Xingjun and Miao, Chenglin and Foo, Chuan Sheng and Low, Bryan Kian Hsiang},<br>  journal={Advances in Neural Information Processing Systems},<br>  volume={34},<br>  pages={16104--16117},<br>  year={2021}<br>}</pre></details> | | |
| [Improving Cooperative Game Theory-based Data Valuation via Data Utility Learning](https://arxiv.org/abs/2107.06336) | Tianhao Wang, Yu Yang, Ruoxi Jia | 2022 | <details><summary>Summary</summary> Wang et al. (2022) propose a general framework to improve effectiveness of sampling-based Shapley value (SV) or Least core (LC) estimation heuristics. They propose learning to predict the performance of a learning algorithm (denoted data utility learning) and using this predictor to estimate learning performance without retraining for cheaper SV and LC estimation. </details> | <details><summary>Bibtex</summary><pre>@article{wang2021improving,<br>  title={Improving cooperative game theory-based data valuation via data utility learning},<br>  author={Wang, Tianhao and Yang, Yu and Jia, Ruoxi},<br>  journal={arXiv preprint arXiv:2107.06336},<br>  year={2021}<br>}</pre></details> | | |
| [Data Banzhaf: A Robust Data Valuation Framework for Machine Learning](https://arxiv.org/abs/2205.15466) | Jiachen T. Wang, Ruoxi Jia | 2023 | <details><summary>Summary</summary> Wang et al. (2023) propose using the Banzhaf value for data valuation, providing better robustness against noisy performance scores and an efficient estimate using Maximum Sample Reuse (MSR) principle </details> | <details><summary>Bibtex</summary><pre>@InProceedings{pmlr-v206-wang23e, title={Data Banzhaf: A Robust Data Valuation Framework for Machine Learning},<br>    author={Wang, Jiachen T. and Jia, Ruoxi},<br>    booktitle={Proceedings of The 26th International Conference on Artificial Intelligence and Statistics},<br>    pages={6388--6421},<br>    year={2023},<br>    editor={Ruiz, Francisco and Dy, Jennifer and van de Meent, Jan-Willem},<br>    volume={206},<br>    series={Proceedings of Machine Learning Research},<br>    month={25--27 Apr},<br>    publisher={PMLR},<br>    pdf={https://proceedings.mlr.press/v206/wang23e/wang23e.pdf},<br>    url={https://proceedings.mlr.press/v206/wang23e.html}<br>}</pre></details> | [💻](https://github.com/Jiachen-T-Wang/data-banzhaf) | |
| [A Multilinear Sampling Algorithm to Estimate Shapley Values](https://arxiv.org/abs/2010.12082) | Ramin Okhrati, Aldo Lipani | 2021 | <details><summary>Summary</summary> Okhrati and Lipani (2021) propose a new sampling method for Shapley values based on a multilinear extension technique as applied in game theory. It provides more accurate estimations of the Shapley values by reducing the variance of the sampling statistics. </details> | <details><summary>Bibtex</summary><pre>@INPROCEEDINGS{9412511,<br>  title={A Multilinear Sampling Algorithm to Estimate Shapley Values},<br>  author={Okhrati, Ramin and Lipani, Aldo},<br>  booktitle={2020 25th International Conference on Pattern Recognition (ICPR)},<br>  year={2021}<br>}</pre></details>  | [💻](https://github.com/aldolipani/OwenShap) | |
| [If You Like Shapley Then You’ll Love the Core](https://ojs.aaai.org/index.php/AAAI/article/view/16721) | Yan, T., and Procaccia, A. D. | 2021 | <details><summary>Summary</summary> Yan and Procaccia (2021) propose an alternative method for credit assignment in data valuation. They use the least core, which can be computed efficiently. </details> | <details><summary>Bibtex</summary><pre>@article{Yan_Procaccia_2021,<br>  title={If You Like Shapley Then You’ll Love the Core},<br>  author={Yan, Tom and Procaccia, Ariel D.},<br>  journal={Proceedings of the AAAI Conference on Artificial Intelligence},<br>  year={2021}<br>}</pre></details>  | | |
| [CS-Shapley: Class-wise Shapley Values for Data Valuation in Classification](https://openreview.net/forum?id=KTOcrOR5mQ9) | Schoch, Stephanie, Haifeng Xu, and Yangfeng Ji | 2022 | <details><summary>Summary</summary> Schoch et al. (2022) propose a new Shapley value that discriminates between training instances' in-class and out-of-class contributions. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{schoch2022csshapley,<br>  title={{CS}-Shapley: Class-wise Shapley Values for Data Valuation in Classification},<br>  author={Stephanie Schoch and Haifeng Xu and Yangfeng Ji},<br>  booktitle={Advances in Neural Information Processing Systems},<br>  year={2022}<br>}</pre></details>  | [💻](https://github.com/uvanlp/valda) | |

#### Efficient algorithms

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Efficient Task-Specific Data Valuation for Nearest Neighbor Algorithms](https://arxiv.org/abs/1908.08619) | Ruoxi Jia, David Dao, Boxin Wang, Frances Ann Hubis, Nezihe Merve Gurel, Bo Li, Ce Zhang, Costas J. Spanos, Dawn Song | 2019 | <details><summary>Summary</summary> Jia et al. (2019) present algorithms to compute the Shapley value exactly in quasi-linear time and approximations in sublinear time for k-nearest-neighbor models. They empirically evaluate their algorithms at scale and extend them to several other settings. </details> | <details><summary>Bibtex</summary><pre>@article{jia12efficient,<br>  title={Efficient Task-Specific Data Valuation for Nearest Neighbor Algorithms},<br>  author={Jia, Ruoxi and Dao, David and Wang, Boxin and Hubis, Frances Ann and Gurel, Nezihe Merve and Zhang, Bo Li4 Ce and Song, Costas Spanos1 Dawn},<br>  journal={Proceedings of the VLDB Endowment},<br>  volume={12},<br>  number={11}<br>}</pre></details> | [💻](https://github.com/easeml/datascope) | |
| [Efficient computation and analysis of distributional Shapley values](https://arxiv.org/abs/2007.01357) | Yongchan Kwon, Manuel A. Rivas, James Zou | 2021 | <details><summary>Summary</summary> Kwon et al. (2021) develop tractable analytic expressions for the distributional data Shapley value for linear regression, binary classification, and non-parametric density estimation as well as new efficient methods for its estimation. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{kwon2021efficient,<br>  title={Efficient computation and analysis of distributional Shapley values},<br>  author={Kwon, Yongchan and Rivas, Manuel A and Zou, James},<br>  booktitle={International Conference on Artificial Intelligence and Statistics},<br>  pages={793--801},<br>  year={2021},<br>  organization={PMLR}<br>}</pre></details> | [💻](https://github.com/ykwon0407/fast_dist_shapley) | |

#### Benchmarks, Criticism & Relaxations

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Scalability vs. Utility: Do We Have to Sacrifice One for the Other in Data Importance Quantification?](https://arxiv.org/abs/1911.07128) | Ruoxi Jia, Fan Wu, Xuehui Sun, Jiacen Xu, David Dao, Bhavya Kailkhura, Ce Zhang, Bo Li, Dawn Song | 2021 | <details><summary>Summary</summary> Jia et al. (2021) perform a theoretical analysis on the differences between leave-one-out-based and Shapley value-based methods as well as an empirical study across several ML tasks investigating the two aforementioned methods as well as exact Shapley value-based methods and Shapley over KNN Surrogates. </details> | <details><summary>Bibtex</summary><pre>@misc{jia2021scalability,<br>      title={Scalability vs. Utility: Do We Have to Sacrifice One for the Other in Data Importance Quantification?}, <br>      author={Ruoxi Jia and Fan Wu and Xuehui Sun and Jiacen Xu and David Dao and Bhavya Kailkhura and Ce Zhang and Bo Li and Dawn Song},<br>      year={2021},<br>      eprint={1911.07128},<br>      archivePrefix={arXiv},<br>      primaryClass={cs.LG}<br>}</pre></details> | [💻](https://github.com/AI-secure/Shapley-Study) | |
| [Shapley values for feature selection: The good, the bad, and the axioms](https://arxiv.org/abs/2102.10936) | Daniel Fryer, Inga Strümke, Hien Nguyen | 2021 | <details><summary>Summary</summary> Fryer et al. (2021) calls into question the appropriateness of using the Shapley value for feature selection and advise caution against the magical thinking that presenting its abstract general axioms as "favourable and fair" may introduce. They further point out that the four axioms of "efficiency", "null player", "symmetry", and "additivity" do not guarantee that the Shapley value is suited to feature selection and may sometimes even imply the opposite. </details> | <details><summary>Bibtex</summary><pre>@misc{fryer2021shapley,<br>      title={Shapley values for feature selection: The good, the bad, and the axioms}, <br>      author={Daniel Fryer and Inga Strümke and Hien Nguyen},<br>      year={2021},<br>      eprint={2102.10936},<br>      archivePrefix={arXiv},<br>      primaryClass={cs.LG}<br>}</pre></details> | | |

### Influence functions & LOO

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Understanding Black-box Predictions via Influence Functions](http://proceedings.mlr.press/v70/koh17a) |  Pang Wei Koh, Percy Liang | 2017 | <details><summary>Summary</summary> Koh & Liang (2017) introduce the use of influence functions, a technique borrowed from robust statistics, to identify training points most responsible for a model's given prediction without needing to retrain. They further develop a simple and efficient implementation of influence functions that scales to large ML settings. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{koh2017understanding,<br>  title={Understanding black-box predictions via influence functions},<br>  author={Koh, Pang Wei and Liang, Percy},<br>  booktitle={International Conference on Machine Learning},<br>  pages={1885--1894},<br>  year={2017},<br>  organization={PMLR}<br>}</pre></details> | [💻](https://bit.ly/gt-influence) | [🎥](https://drive.google.com/open?id=1ZLY_9Wsk9MA0kXAoJDd6o1gbLvHhyPAn) |
| [On the accuracy of influence functions for measuring group effects](https://arxiv.org/abs/1905.13289) | Pang Wei Koh*, Kai-Siang Ang*, Hubert H. K. Teo*, and Percy Liang | 2019 | <details><summary>Summary</summary> Koh et al. (2019) study influence functions to measure effects of large groups of training points instead of individual points. They empirically find a correlation and often underestimation between predicted and actual effects and theoretically show that this need not hold in general, realistic settings. </details> | <details><summary>Bibtex</summary><pre>@article{koh2019accuracy,<br>  title={On the accuracy of influence functions for measuring group effects},<br>  author={Koh, Pang Wei and Ang, Kai-Siang and Teo, Hubert HK and Liang, Percy},<br>  journal={arXiv preprint arXiv:1905.13289},<br>  year={2019}<br>}</pre></details> | [💻](https://github.com/kohpangwei/group-influence-release) | [🎥](https://drive.google.com/open?id=1ZLY_9Wsk9MA0kXAoJDd6o1gbLvHhyPAn) |
| [Scaling Up Influence Functions](https://arxiv.org/abs/2112.03052) | Schioppa, Andrea, Polina Zablotskaia, David Vilar, and Artem Sokolov | 2022 | <details><summary>Summary</summary> Schioppa et al. (2022) propose a new method to scale the computation of influence functions for large neural networks using the Arnoldi iteration. With this, they achieve successful implementation of influence functions on full-size Transformer models with hundreds of millions of parameters. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{schioppa2022scaling,<br>  title={Scaling Up Influence Functions},<br>  author={Schioppa, Andrea and Zablotskaia, Polina and Vilar, David and Sokolov, Artem},<br>  booktitle={Proceedings of the AAAI Conference on Artificial Intelligence},<br>  year={2022}<br>}</pre></details> | [💻](https://github.com/google-research/jax-influence) | |
| [Studying large language model generalization with influence functions](https://arxiv.org/abs/2308.03296) | Grosse, Roger and Bae, Juhan and Anil, Cem and Elhage, Nelson and Tamkin, Alex and Tajdini, Amirhossein and Steiner, Benoit and Li, Dustin and Durmus, Esin and Perez, Ethan and others | 2023 | <details><summary>Summary</summary> Grosse et al. (2023) use a method known as EK-FAC to approximate the Hessian of the loss of large language models. They apply this technique to study influence functions on large language models, up to 50 billion parameters. </details> | <details><summary>Bibtex</summary><pre>@article{grosse2023studying,<br>  title={Studying large language model generalization with influence functions},<br>  author={Grosse, Roger and Bae, Juhan and Anil, Cem and Elhage, Nelson and Tamkin, Alex and Tajdini, Amirhossein and Steiner, Benoit and Li, Dustin and Durmus, Esin and Perez, Ethan and others},<br>  journal={arXiv preprint arXiv:2308.03296},<br>  year={2023}<br>}</pre></details> | | |


### Reinforcement Learning

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Data Valuation using Reinforcement Learning](https://proceedings.mlr.press/v119/yoon20a.html) | Jinsung Yoon, Sercan Ö Arık, Tomas Pfister | 2020 | <details><summary>Summary</summary> Yoon et al. (2020) propose using reinforcement learning for data valuation to learn data values jointly with the predictor model. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{49189,<br>  title={Data Valuation using Reinforcement Learning},<br>  author={Jinsung Yoon and Sercan Arik and Tomas Pfister},<br>  year={2020}<br>}</pre></details> | [💻](https://github.com/google-research/google-research/tree/master/dvrl) | [🎥](https://icml.cc/media/icml-2020/Slides/6276.pdf) |

### Deep Neural Networks

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [DAVINZ: Data Valuation using Deep Neural Networks at Initialization](https://proceedings.mlr.press/v162/wu22j.html) | Zhaoxuan Wu, Yao Shu, Bryan Kian Hsiang Low | 2022 | <details><summary>Summary</summary> Wu et al. (2022) introduce a validation-based and training-free method for efficient data valuation with large and complex deep neural networks (DNNs). They derive and exploit a domain-aware generalization bound for DNNs to characterize their performance without training and uses this bound as the scoring function while keeping conventional techniques such as Shapley values as the valuation function. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{wu2022davinz,<br>  title={DAVINZ: Data Valuation using Deep Neural Networks at Initialization},<br>  author={Wu, Zhaoxuan and Shu, Yao and Low, Bryan Kian Hsiang},<br>  booktitle={International Conference on Machine Learning},<br>  pages={24150--24176},<br>  year={2022},<br>  organization={PMLR}<br>}</pre></details> | | [🎥](https://icml.cc/media/icml-2022/Slides/17500.pdf) |

### Out-of-Bag score
| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Data-OOB: Out-of-bag Estimate as a Simple and Efficient Data Value](https://arxiv.org/abs/2304.07718) | Yongchan Kwon, James Zou | 2023 | <details><summary>Summary</summary> Kwon et al. (2023) propose using the out-of-bag estimate of a bagging estimator for computationally efficient data valuation. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{DBLP:conf/icml/Kwon023, <br>    author={Yongchan Kwon and James Zou}, <br>    editor={Andreas Krause and Emma Brunskill and Kyunghyun Cho and Barbara Engelhardt and Sivan Sabato and Jonathan Scarlett},<br>    title={Data-OOB: Out-of-bag Estimate as a Simple and Efficient Data Value},<br>    booktitle={International Conference on Machine Learning, {ICML} 2023, 23-29 July 2023, Honolulu, Hawaii, {USA}}, <br>    series={Proceedings of Machine Learning Research}, <br>    volume={202}, <br>    pages={18135--18152},<br>    publisher={{PMLR}}, <br>    year={2023}, <br>    url={https://proceedings.mlr.press/v202/kwon23e.html}, <br>    timestamp={Mon, 28 Aug 2023 17:23:08 +0200}, <br>    biburl={https://dblp.org/rec/conf/icml/Kwon023.bib}, <br>    bibsource={dblp computer science bibliography, https://dblp.org} <br>}</pre></details> | [💻](https://github.com/ykwon0407/STAT5206_Fall_2023) | [🎥](https://icml.cc/virtual/2023/poster/23689) |


## Benchmarks

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [OpenDataVal: a Unified Benchmark for Data Valuations](https://arxiv.org/abs/2306.10577) | Kevin Jiang, Weixin Liang, James Zou, Yongchan Kwon | 2023 | <details><summary>Summary</summary> Jiang et al. (2023) provides a Python library to build and test data evaluators across different datasets, data evaluators, models, and new benchmarks. </details> | <details><summary>Bibtex</summary><pre>@article{jiang2023opendataval,<br>      title={OpenDataVal: a Unified Benchmark for Data Valuation},<br>      author={Kevin Fu Jiang and Weixin Liang and James Zou and Yongchan Kwon},<br>      booktitle={Thirty-seventh Conference on Neural Information Processing Systems Datasets and Benchmarks Track},<br>      year={2023},<br>url={https://openreview.net/forum?id=eEK99egXeB}<br>}</pre></details> | [💻](https://github.com/opendataval/opendataval) | [🎥](https://neurips.cc/virtual/2023/poster/73521) |

## Libraries
| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [influenciae](https://github.com/deel-ai/influenciae) | Deel-AI | 2023 | <details><summary>Summary</summary> A stable implementation of influence functions in tensorflow. </details> | <details><summary>Bibtex</summary><pre></pre></details> | [💻](https://github.com/deel-ai/influenciae) | |
| [pyDVL](https://github.com/aai-institute/pyDVL) | appliedAI Institute | 2023 | <details><summary>Summary</summary> A library of stable and efficient implementations of algorithms for computing Shapley values and influence functions in pytorch. </details> | <details><summary>Bibtex</summary><pre></pre></details> | [💻](https://github.com/aai-institute/pyDVL) | |


### Surveys

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Data Valuation in Machine Learning: “Ingredients”, Strategies, and Open Challenges](https://www.ijcai.org/proceedings/2022/782) | Rachael Hwee Ling Sim*, Xinyi Xu*, Bryan Kian Hsiang Low | 2022 | <details><summary>Summary</summary> Sim et al. (2022) present a technical survey of data valuation and its "ingredients" and properties. The paper outlines common desiderata as well as some open research challenges. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{sim2022data,<br>  title={Data valuation in machine learning:“ingredients”, strategies, and open challenges},<br>  author={Sim, Rachael Hwee Ling and Xu, Xinyi and Low, Bryan Kian Hsiang},<br>  booktitle={Proc. IJCAI},<br>  year={2022}<br>}</pre></details> | | [🎥](https://xinyi-xu.com/ijcai_slides.pdf) |


## Designing data marketplaces

### Data market system designs

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [A demonstration of sterling: a privacy-preserving data marketplace](http://www.vldb.org/pvldb/vol11/p2086-hynes.pdf) | Nick Hynes, David Dao, David Yan, Raymond Cheng, Dawn Song | 2018 | | <details><summary>Bibtex</summary><pre>@article{hynes2018demonstration,<br>  title={A Demonstration of Sterling: A Privacy-Preserving Data Marketplace},<br>  author={Hynes, Nick and Dao, David and Yan, David and Cheng, Raymond and Song, Dawn},<br>  journal={Proceedings of the VLDB Endowment},<br>  volume={11},<br>  number={12},<br>  year={2018}<br>}</pre></details> | | |
| [DataBright: Towards a Global Exchange for Decentralized Data Ownership and Trusted Computation](https://arxiv.org/abs/1802.04780) | David Dao, Dan Alistarh, Claudiu Musat, Ce Zhang | 2018 | | <details><summary>Bibtex</summary><pre>@article{dao2018databright,<br>  title={Databright: Towards a global exchange for decentralized data ownership and trusted computation},<br>  author={Dao, David and Alistarh, Dan and Musat, Claudiu and Zhang, Ce},<br>  journal={arXiv preprint arXiv:1802.04780},<br>  year={2018}<br>}</pre></details> | | |
| [A Marketplace for Data: An Algorithmic Solution](https://arxiv.org/abs/1805.08125) | Anish Agarwal, Munther Dahleh, Tuhin Sarkar | 2019 | | <details><summary>Bibtex</summary><pre>@inproceedings{agarwal2019marketplace,<br>  title={A marketplace for data: An algorithmic solution},<br>  author={Agarwal, Anish and Dahleh, Munther and Sarkar, Tuhin},<br>  booktitle={Proceedings of the 2019 ACM Conference on Economics and Computation},<br>  pages={701--726},<br>  year={2019}<br>}</pre></details> | | |
| [Computing a Data Dividend](https://arxiv.org/abs/1905.01805) | Eric Bax | 2019 | | <details><summary>Bibtex</summary><pre>@misc{bax2019computing,<br>      title={Computing a Data Dividend}, <br>      author={Eric Bax},<br>      year={2019},<br>      eprint={1905.01805},<br>      archivePrefix={arXiv},<br>      primaryClass={cs.GT}<br>}</pre></details> | | |
| [Incentivizing Collaboration in Machine Learning via Synthetic Data Rewards](https://arxiv.org/pdf/2112.09327.pdf) | Sebastian Shenghong Tay, Xinyi Xu, Chuan Sheng Foo, Bryan Kian Hsiang Low | 2021 | | <details><summary>Bibtex</summary><pre>@article{tay2021incentivizing,<br>  title={Incentivizing Collaboration in Machine Learning via Synthetic Data Rewards},<br>  author={Tay, Sebastian Shenghong and Xu, Xinyi and Foo, Chuan Sheng and Low, Bryan Kian Hsiang},<br>  journal={arXiv preprint arXiv:2112.09327},<br>  year={2021}<br>}</pre></details> | | |

### Automatic data compliance

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Data Capsule: A New Paradigm for Automatic Compliance with Data Privacy Regulations](https://arxiv.org/abs/1909.00077) | Lun Wang, Joseph P. Near, Neel Somani, Peng Gao, Andrew Low, David Dao, Dawn Song | 2019 | | <details><summary>Bibtex</summary><pre>@misc{wang2019data,<br>      title={Data Capsule: A New Paradigm for Automatic Compliance with Data Privacy Regulations}, <br>      author={Lun Wang and Joseph P. Near and Neel Somani and Peng Gao and Andrew Low and David Dao and Dawn Song},<br>      year={2019},<br>      eprint={1909.00077},<br>      archivePrefix={arXiv},<br>      primaryClass={cs.CY}<br>}</pre></details> | [💻](https://github.com/sunblaze-ucb/Data-Capsule) | |

### Data valuation applications

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [A Principled Approach to Data Valuation for Federated Learning](https://arxiv.org/abs/2009.06192) | Tianhao Wang, Johannes Rausch, Ce Zhang, Ruoxi Jia, Dawn Song | 2020 | | <details><summary>Bibtex</summary><pre>@misc{wang2020principled,<br>      title={A Principled Approach to Data Valuation for Federated Learning}, <br>      author={Tianhao Wang and Johannes Rausch and Ce Zhang and Ruoxi Jia and Dawn Song},<br>      year={2020},<br>      eprint={2009.06192},<br>      archivePrefix={arXiv},<br>      primaryClass={cs.LG}<br>}</pre></details> | | |
| [Data valuation for medical imaging using Shapley value and application to a large-scale chest X-ray dataset](https://www.nature.com/articles/s41598-021-87762-2) | Siyi Tang, Amirata Ghorbani, Rikiya Yamashita, Sameer Rehman, Jared A Dunnmon, James Zou, Daniel L Rubin | 2021 | | <details><summary>Bibtex</summary><pre>@article{tang2021data,<br>  title={Data valuation for medical imaging using Shapley value and application to a large-scale chest X-ray dataset},<br>  author={Tang, Siyi and Ghorbani, Amirata and Yamashita, Rikiya and Rehman, Sameer and Dunnmon, Jared A and Zou, James and Rubin, Daniel L},<br>  journal={Scientific reports},<br>  volume={11},<br>  number={1},<br>  pages={1--9},<br>  year={2021},<br>  publisher={Nature Publishing Group}<br>}</pre></details> | | |


## Data markets and society

### Economics of Data

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Nonrivalry and the Economics of Data](https://www.gsb.stanford.edu/faculty-research/working-papers/nonrivalry-economics-data) | Charles I. Jones, Christopher Tonetti | 2019 | | <details><summary>Bibtex</summary><pre>@article{10.1257/aer.20191330,<br>  Author = {Jones, Charles I. and Tonetti, Christopher},<br>  Title = {Nonrivalry and the Economics of Data},<br>  Journal = {American Economic Review},<br>  Volume = {110},<br>  Number = {9},<br>  Year = {2020},<br>  Month = {September},<br>  Pages = {2819-58},<br>  DOI = {10.1257/aer.20191330},<br>  URL = {https://www.aeaweb.org/articles?id=10.1257/aer.20191330}<br>}</pre></details> | | |


### Data Dignity

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Chapter 5: Data as Labor, Radical Markets](https://www.degruyter.com/document/doi/10.1515/9780691196978/html) | Eric A. Posner and E Glen Weyl | 2019 | | <details><summary>Bibtex</summary><pre>@book{posner2019radical,<br>  title={Radical Markets},<br>  author={Posner, Eric A and Weyl, E Glen},<br>  year={2019},<br>  publisher={Princeton University Press}<br>}</pre></details> | | |
| [Should We Treat Data as Labor? Moving beyond "Free"](https://www.aeaweb.org/articles?id=10.1257/pandp.20181003) | Imanol Arrieta-Ibarra, Leonard Goff, Diego Jiménez-Hernández, Jaron Lanier, E. Glen Weyl | 2018 | | <details><summary>Bibtex</summary><pre>@article{10.1257/pandp.20181003,<br>  Author = {Arrieta-Ibarra, Imanol and Goff, Leonard and Jiménez-Hernández, Diego and Lanier, Jaron and Weyl, E. Glen},<br>  Title = {Should We Treat Data as Labor? Moving beyond "Free"},<br>  Journal = {AEA Papers and Proceedings},<br>  Volume = {108},<br>  Year = {2018},<br>  Month = {May},<br>  Pages = {38-42},<br>  DOI = {10.1257/pandp.20181003},<br>  URL = {https://www.aeaweb.org/articles?id=10.1257/pandp.20181003}<br>}</pre></details> | | |


## Strategic adaptation

### Performative prediction

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Performative Prediction](https://proceedings.mlr.press/v119/perdomo20a.html) | Juan Perdomo, Tijana Zrnic, Celestine Mendler-Dünner, Moritz Hardt | 2020 | <details><summary>Summary</summary> Perdomo et al. (2020) introduce the concept of "performative prediction" dealing with predictions that influence the target they aim to predict, e.g. through taking actions based on the predictions, causing a distribution shift. The authors develop a risk minimization framework for performative prediction and introduce the equilibrium notion of performative stability where predictions are calibrated against future outcomes that manifest from acting on the prediction. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{perdomo2020performative,<br>  title={Performative prediction},<br>  author={Perdomo, Juan and Zrnic, Tijana and Mendler-D{\"u}nner, Celestine and Hardt, Moritz},<br>  booktitle={International Conference on Machine Learning},<br>  pages={7599--7609},<br>  year={2020},<br>  organization={PMLR}<br>}</pre> </details> | | |
| [Stochastic Optimization for Performative Prediction](https://papers.nips.cc/paper/2020/hash/33e75ff09dd601bbe69f351039152189-Abstract.html) | Celestine Mendler-Dünner, Juan Perdomo, Tijana Zrnic, Moritz Hardt | 2020 | <details><summary>Summary</summary> Mendler-Dünner et al. (2020) look at stochastic optimization for performative prediction and prove convergence rates for greedily deploying models after each stochastic update (which may cause distribution shift affecting convergence to a stability point) or lazily deploying the model after several updates. </details> | <details><summary>Bibtex</summary><pre>@article{mendler2020stochastic,<br>  title={Stochastic optimization for performative prediction},<br>  author={Mendler-D{\"u}nner, Celestine and Perdomo, Juan and Zrnic, Tijana and Hardt, Moritz},<br>  journal={Advances in Neural Information Processing Systems},<br>  volume={33},<br>  pages={4929--4939},<br>  year={2020}<br>}</pre> </details> | | |

### Strategic classification

| | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| [Strategic Classification is Causal Modeling in Disguise](http://proceedings.mlr.press/v119/miller20b) | John Miller, Smitha Milli, Moritz Hardt | 2020 | <details><summary>Summary</summary> Miller et al. (2020) argue that strategic classication involves causal modelling and designing incentives for improvement requires solving a non-trivial causal inference problem. The authors provide a distinction between gaming and improvement as well as provide a causal framework for strategic adaptation. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{miller2020strategic,<br>  title={Strategic classification is causal modeling in disguise},<br>  author={Miller, John and Milli, Smitha and Hardt, Moritz},<br>  booktitle={International Conference on Machine Learning},<br>  pages={6917--6926},<br>  year={2020},<br>  organization={PMLR}<br>}</pre> </details> | | |
| [Alternative Microfoundations for Strategic Classification](http://proceedings.mlr.press/v139/jagadeesan21a) | Meena Jagadeesan, Celestine Mendler-Dünner, Moritz Hardt | 2021 | <details> <summary>Summary</summary> Jagadeesan et al. (2021) show that standard microfoundations in strategic classification, that typically uses individual-level behaviour to deduce aggregate-level responses, can lead to degenerate behaviour in aggregate: discontinuities in the aggregate response, stable points ceasing to exist, and maximizing social burden. The authors introduce a noisy response model inspired by performative prediction that mitigates these limitations for binary classification. </details> | <details><summary>Bibtex</summary><pre>@inproceedings{jagadeesan2021alternative,<br>  title={Alternative microfoundations for strategic classification},<br>  author={Jagadeesan, Meena and Mendler-D{\"u}nner, Celestine and Hardt, Moritz},<br>  booktitle={International Conference on Machine Learning},<br>  pages={4687--4697},<br>  year={2021},<br>  organization={PMLR}<br>}</pre></details> | | |


## Data Valuation Researchers

| Name | Institute | h-index |
|------|-----------|---------|
| [Costas Spanos](https://scholar.google.com/citations?hl=en&user=90TaOdoAAAAJ) | University of California, Berkeley | 61 |
| [Jinsung Yoon](https://scholar.google.com/citations?hl=en&user=kiFd6A8AAAAJ) | Google Cloud AI | 33 |
| [Tomas Pfister](https://scholar.google.com/citations?hl=en&user=ahSpJOAAAAAJ) | Google Cloud AI | 39 |
| [Amirata Ghorbani](https://scholar.google.com/citations?hl=en&user=BtgIFycAAAAJ) | Stanford | 18 |
| [James Zou](https://scholar.google.com/citations?hl=en&user=23ZXZvEAAAAJ) | Stanford | 64 |
| [Nektaria Tryfona](https://scholar.google.com/citations?hl=en&user=l8oLKs8AAAAJ) | Virginia Tech | 27 |
| [Rachael Hwee Ling Sim](https://scholar.google.com/citations?hl=en&user=OSpv414AAAAJ) | National University of Singapore | 4 |
| [Bryan Kian Hsiang Low](https://scholar.google.com/citations?hl=en&user=2P-Q09UAAAAJ) | National University of Singapore | 38 |
| [Dawn Song](https://scholar.google.com/citations?hl=en&user=84WzBlYAAAAJ) | University of California, Berkeley | 142 |
| [Zhaoxuan Wu](https://scholar.google.com/citations?hl=en&user=Th_mPm8AAAAJ) | National University of Singapore | 4 |
| [Xinyi Xu](https://scholar.google.com/citations?user=2762GgsAAAAJ&hl=en) | National University of Singapore | 8 |
| [Tianhao Wang](https://scholar.google.com/citations?hl=en&user=TkgyXGwAAAAJ) | University of Virginia | 18 |
| [José González Cabañas](https://scholar.google.com/citations?hl=en&user=NZQ0lL8AAAAJ) | UC3M-Santander Big Data Institute | 7 |
| [Ruben Cuevas Rumin](https://scholar.google.com/citations?hl=en&user=lGuDTyAAAAAJ) | Universidad Carlos III de Madrid | 26 |
| [Jiachen T. Wang](https://scholar.google.com/citations?hl=en&user=nvQOtgkAAAAJ) | Princeton University | 9 |
| [Bohong Wang](https://scholar.google.com/citations?hl=en&user=NTUthMMAAAAJ) | Tsinghua University | 6 |
| [Yongchan Kwon](https://scholar.google.com/citations?hl=en&user=PElI4ikAAAAJ) | Columbia University | 10 |
| [Siyi Tang](https://scholar.google.com/citations?hl=en&user=dpRSfnoAAAAJ) | Artera | 8 |
| [Li Xiong](https://scholar.google.com/citations?hl=en&user=jJ8BLgsAAAAJ) | Emory University | 52 |
| [Jessica Vitak](https://scholar.google.com/citations?user=RC9bN7kAAAAJ&hl=en) | University of Maryland | 49 |
| [Katie Chamberlain Kritikos](https://scholar.google.com/citations?hl=en&user=GzaVacsAAAAJ) | University of Illinois at Urbana-Champaign | 6 |
| [Zhenan Fan](https://scholar.google.com/citations?hl=en&user=un31cHUAAAAJ) | Huawei Technologies Canada | 6 |
| [Shuyue Wei](https://scholar.google.com/citations?hl=en&user=JH1mkD4AAAAJ) | Beihang University | 4 |
| [Hannah Stein](https://scholar.google.com/citations?hl=en&user=H1dRqaMAAAAJ) | Saarland University | 3 |
| [Wolfgang Maass](https://scholar.google.com/citations?hl=en&user=v1qq9joAAAAJ) | Saarland University | 26 |
| [Mohammad Mohammadi Amiri](https://scholar.google.com/citations?hl=en&user=jpJy6SEAAAAJ) | Rensselaer Polytechnic Institute | 18 |
| [Ramesh Raskar](https://scholar.google.com/citations?hl=en&user=8hpOmVgAAAAJ) | MIT | 103 |
| [Konstantin D. Pandl](https://scholar.google.com/citations?hl=en&user=hcn6_a8AAAAJ) | Karlsruhe Institute of Technolgoy | 6 |
| [Ali Sunyaev](https://scholar.google.com/citations?hl=en&user=Uc8sVecAAAAJ) | Karlsruhe Institute of Technolgoy | 43 |
| [Ludovico Boratto](https://scholar.google.com/citations?hl=en&user=1unjC10AAAAJ) | University of Cagliari | 25 |
| [han xiao](https://scholar.google.com/citations?hl=en&user=ZBibCxIAAAAJ) | | 70 |
| [Junjie Wu](https://scholar.google.com/citations?hl=en&user=mLZcym8AAAAJ) | Center for High Pressure Science & Technology Advanced Research | 55 |
| [Xiao Tian](https://scholar.google.com/citations?hl=en&user=FdGSDcQAAAAJ) | National University of Singapore | 1 |
| [Kean Birch](https://scholar.google.com/citations?hl=en&user=wKYYL5MAAAAJ) | Institute for Technoscience & Society | 40 |
| [Callum Ward](https://scholar.google.com/citations?hl=en&user=icnaSlUAAAAJ) | Uppsala University | 10 |
| [Praveer Singh](https://scholar.google.com/citations?hl=en&user=12RkAfQAAAAJ) | University of Colorado School of Medicine | 19 |
| [Anran Xu](https://scholar.google.com/citations?hl=en&user=ptQB7KEAAAAJ) | Shanghai Jiao Tong University | 2 |
| [Guihai Chen](https://scholar.google.com/citations?hl=en&user=rqZWbYgAAAAJ) | | 67 |
| [Andre Esteva](https://scholar.google.com/citations?hl=en&user=MN8r_gMAAAAJ) | Co-Founder & CEO, Artera | 23 |
| [Prateek Mittal](https://scholar.google.com/citations?hl=en&user=xTKD8J4AAAAJ) | Princeton University | 55 |
| [Hyeontaek Oh](https://scholar.google.com/citations?hl=en&user=iTt4_Z0AAAAJ) | Institute for IT Convergence | 9 |
| [Lingjiao Chen](https://scholar.google.com/citations?hl=en&user=1rPi_78AAAAJ) | Stanford | 13 |
| [Xiangyu Chang](https://scholar.google.com/citations?hl=en&user=IWIQ64YAAAAJ) | Xi'an Jiaotong University | 17 |
| [Hoang Anh Just](https://scholar.google.com/citations?hl=en&user=XcBDQhAAAAAJ) | Virginia Tech | 3 |
| [David Dao](https://scholar.google.com/citations?hl=en&user=XHeNA_8AAAAJ) | ETH | 13 |
| [Mark Mazumder](https://scholar.google.com/citations?hl=en&user=kM8TYfoAAAAJ) | Harvard | 12 |
| [Vijay Janapa Reddi](https://scholar.google.com/citations?hl=en&user=gy4UVGcAAAAJ) | Harvard | 46 |
| [Sabri Eyuboglu](https://scholar.google.com/citations?hl=en&user=ya1egC8AAAAJ) | Stanford | 6 |
| [Wenqian Li](https://scholar.google.com/citations?hl=en&user=QO3W0sMAAAAJ) | National University of Singapore | 2 |
