# Resources

Everything here is free. **Bold** items are the ones to read first; the rest are for when you want to go deeper.

---

## Week 0: Starter pack (before the project starts)

**Do:** [`notebooks/week0_starter_pack.ipynb`](notebooks/week0_starter_pack.ipynb). It has 17 short exercises that check themselves, covering Python, NumPy, Pandas, plotting and ML basics. Plan on about 6 to 8 hours.

If something in the notebook is new to you, learn it here:

| Topic | Start here | Then |
|---|---|---|
| Python basics | **[W3Schools Python Tutorial](https://www.w3schools.com/python/)**: work through *Lists*, *Dictionaries*, *For Loops*, *Functions* | [Kaggle Learn: Python](https://www.kaggle.com/learn/python) |
| NumPy | **[W3Schools NumPy Tutorial](https://www.w3schools.com/python/numpy/default.asp)** | [NumPy: the absolute basics for beginners](https://numpy.org/doc/stable/user/absolute_beginners.html) |
| Pandas | **[Kaggle Learn: Pandas](https://www.kaggle.com/learn/pandas)** | [W3Schools Pandas Tutorial](https://www.w3schools.com/python/pandas/default.asp) |
| Plotting | **[W3Schools Matplotlib Tutorial](https://www.w3schools.com/python/matplotlib_intro.asp)** | [Kaggle Learn: Data Visualization](https://www.kaggle.com/learn/data-visualization) |
| Machine learning | **[Kaggle Learn: Intro to Machine Learning](https://www.kaggle.com/learn/intro-to-machine-learning)** | [Google Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course) · [scikit-learn: Getting Started](https://scikit-learn.org/stable/getting_started.html) |
| ML intuition (videos) | **[StatQuest](https://www.youtube.com/@statquest)**: search "logistic regression", "decision trees", "bias and variance" | |

---

## Week 1: Markets and order books

**Do:** [`notebooks/week1_order_books.ipynb`](notebooks/week1_order_books.ipynb)

- **[Zerodha Varsity: Introduction to Stock Markets](https://zerodha.com/varsity/module/introduction-to-stock-markets/)**: a friendly beginner's guide to how markets work.
- [Cont, Kukanov & Stoikov, *The Price Impact of Order Book Events*](https://arxiv.org/abs/1011.6402): introduces **order flow imbalance**, the idea behind the Week 1 signal. Read the introduction and look at the figures.
- Bouchaud, Bonart, Donier & Gould, *Trades, Quotes and Prices* (Cambridge, 2018), chapters 1 to 3: for anyone who wants the full picture.

## Week 2: Your trading bot (rules first, then ML)

- **[scikit-learn User Guide](https://scikit-learn.org/stable/user_guide.html)**: logistic regression, gradient boosting, cross-validation.
- [Kaggle Learn: Intermediate Machine Learning](https://www.kaggle.com/learn/intermediate-machine-learning): pipelines, data leakage, gradient boosting.
- [Ntakaris et al., *Benchmark Dataset for Mid-Price Forecasting of Limit Order Book Data*](https://arxiv.org/abs/1705.03233): the paper behind **FI-2010**, the real order book dataset we use.
- [Zhang, Zohren & Roberts, *DeepLOB*](https://arxiv.org/abs/1808.03668): deep learning on order books, optional for the curious.

## Week 3: The attacker (spoofing)

- **[US Department of Justice: the 2010 Flash Crash spoofing case](https://www.justice.gov/archives/opa/pr/futures-trader-pleads-guilty-illegally-manipulating-futures-market-connection-2010-flash)**: the real story this project starts from.
- **[Wang & Wellman, *Spoofing the Limit Order Book: An Agent-Based Model* (AAMAS 2017)](https://ifmas.csc.liv.ac.uk/Proceedings/aamas2017/pdfs/p651.pdf)**: almost exactly our setup, a spoofer in a simulated market full of agents.

## Week 4: Smarter attacks

- **[Goldblum et al., *Adversarial Attacks on Machine Learning Systems for High-Frequency Trading* (ICAIF 2021)](https://arxiv.org/abs/2002.09565)**: the closest paper to this project.
- [Goodfellow, Shlens & Szegedy, *Explaining and Harnessing Adversarial Examples*](https://arxiv.org/abs/1412.6572): the classic adversarial attack (FGSM).
- RL stretch goal: [OpenAI Spinning Up](https://spinningup.openai.com/en/latest/) (intro sections) · [Gymnasium](https://gymnasium.farama.org/) · [Stable-Baselines3](https://stable-baselines3.readthedocs.io/)

## Week 5: Defenses

- **[scikit-learn: Novelty and Outlier Detection](https://scikit-learn.org/stable/modules/outlier_detection.html)**: Isolation Forest and friends, for the manipulation detector.
- [Madry et al., *Towards Deep Learning Models Resistant to Adversarial Attacks*](https://arxiv.org/abs/1706.06083): adversarial training.
- [Wang, Vorobeychik & Wellman, *A Cloaking Mechanism to Mitigate Market Manipulation* (IJCAI 2018)](https://www.ijcai.org/proceedings/2018/75): a market-design defense against spoofing.

## Week 6: Tournament and final report

No new reading this week. Use everything above.
