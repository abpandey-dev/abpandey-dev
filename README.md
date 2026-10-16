# Hi, I'm Abhishek 👋

### QA → AI Engineer · Building reliable AI with a tester's mindset

I'm an **SDET-2 at Deutsche Telekom Digital Labs** with **6+ years** in software quality engineering, now moving into **AI engineering**. I've spent years testing apps, APIs and big-data pipelines, and now I'm building LLM apps, agents and automation, with testing and evaluation built in from the start.

> *Ideas → Experiments → Impact* ☕ Fueled by chai & ideas.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-abpandey--ai-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abpandey-ai/)
![Focus](https://img.shields.io/badge/Focus-AI%20Agents%20%C2%B7%20RAG%20%C2%B7%20LLM%20Apps-7C3AED?style=for-the-badge)

---

## 📌 Featured projects

**🧠 [Agent Memory Engine](https://github.com/abpandey-dev/agent-memory-engine)**: long-term memory for AI agents, served over **MCP** so Claude Code or any agent can use it. Claude extracts facts from conversations and decides whether each is new, an update (the old fact is kept as history) or already known. Recall blends keyword search with an entity graph.

- Benchmark on 72 questions: **memory engine 100% · whole history in the prompt 100% · search over raw chat logs 25% · no memory 17%**. With 32 conversations the memory engine needs **9× fewer tokens** per question than pasting the history.
- Says "I don't know" instead of guessing (12/12 never-mentioned facts), and answers both "where do I live?" and "where did I live before?".

**🗜️ [Context Compressor](https://github.com/abpandey-dev/context-compressor)**: shrinks what tools hand an LLM (API JSON, logs, documents) before it reaches the model, and measures whether the answers survive. Lossless JSON tables, log pattern mining and BM25 selection, with zero dependencies.

- Benchmark on 53 questions over real GitHub API responses, TRAI data and a 1,700-line incident log (Claude Haiku 5.5): **82% fewer tokens, 52/53 correct, the same as uncompressed**. The log drops from 91K to 2.2K tokens.
- **What breaks:** query-based selection falls to 61% on counts and totals, and Claude's own summaries round numbers ("about 48" for 47). On the full raw log the model miscounted; the precomputed pattern count was exact.

**📡 [NOC Copilot](https://github.com/abpandey-dev/noc-copilot)**: agentic AI for 5G network operations. A Claude agent investigates network incidents (alarms, KPIs, change logs) with read-only tools, finds the root cause and proposes fixes for human approval, with EU AI Act-style oversight and an audit trail.

- Standard benchmark vs a classic alarm-rule baseline: **rules 60% · Claude Haiku 5.5 100% at $0.0023 per incident**, including incidents where the key alarm never arrived.
- v0.2 hard suite (two faults at once, cascading failures, planned-maintenance decoys): **rules 30% · Haiku 100%**. A prompt ablation showed one line of NOC domain knowledge ("planned work is not a fault") stops the agent blaming a maintenance site.
- v0.3 messy telemetry (alarm storms, missing KPI data, faults an hour apart, busy-hour masking): **rules 55% · Haiku 100% at $0.0041 per incident**, even with no domain hints in the prompt. The anomaly detector missed the early fault in every staggered incident; the agent found it from the change log, alarms and KPI history.

**📶 [Telco Churn Copilot](https://github.com/abpandey-dev/telco-churn-copilot)**: ML + RAG + LLM for customer retention. Predicts which mobile customers will leave, explains why, and answers retention questions from company policy, with every citation checked against what was actually retrieved.

- **ML:** logistic regression (ROC-AUC 0.756) beats gradient boosting (0.716); the model recovers the 6 true churn drivers built into the data. Cologne churns most, but the cause is its network, not the city.
- **RAG:** policy search measured on 15 questions (hit@3 87%); copilot answers checked against GDPR, offer and compensation rules, about $0.001-0.003 per answer with Claude Haiku 5.5.

**📶 [Jio vs Airtel](https://github.com/abpandey-dev/telecom-india)**: India's mobile market from TRAI's own monthly reports. 31 months x 22 circles extracted from 30 PDFs (ruled, sideways and scanned tables), every operator-month checked against TRAI's totals.

- **Caught a definition change:** in Dec 2025 TRAI started counting machine (M2M) SIMs, adding **68.5M** to Airtel overnight. On consumer SIMs, **Jio's lead grew from 70M to 76M** (41.8% vs 35.2%).
- July 2024 tariff hikes: **Jio lost 16.5M** subscribers in four months while BSNL gained 6.8M; Jio won them all back. Only **57% of BSNL's SIMs** are active.
- **Ask the data with Claude:** a `telecom-ask` agent answers plain-English questions through 7 read-only tools, and every number in its answer is checked against the tool outputs. It caught a wrong average in my own README (1.35M, not 1.55M monthly net adds). About $0.002 per question.

**🎬 [Netflix Insights](https://github.com/abpandey-dev/netflix-insights)**: what the world actually watches. 17,370 titles and 23.4B views from Netflix's own published data, matched to IMDb (88% of views), plus three recommenders tested against each other.

- **Best-rated and most-watched directors don't overlap**: Jackson, Tarantino, Nolan vs the directors of new Netflix releases (*War Machine*, *The Rip*). The top 1% of titles get 22% of all views; ratings barely predict views.
- **Recommenders, measured:** "watched by the same audiences" (collaborative) beats genre similarity **16.7% vs 2.3%** recall@20, which is why Netflix leans on viewing behaviour.

**🚆 [Rail Punctuality](https://github.com/abpandey-dev/rail-punctuality)**: how late are India's long-distance trains? Six months of real running history for 136 trains (20,461 runs), collected politely, validated against the source and analysed with pandas.

- Rajdhani, Shatabdi and Vande Bharat are on time **~80%** of the time; Mail/Express **45%**. Average delay **41 min**, median **6 min**.
- **10 trains via Kharagpur-Tatanagar-Rourkela cause 30% of all runs over an hour late** (186 min average vs 30 min for the rest). 83% of runs win back ~15 min on the final leg thanks to timetable padding.

**🧪 [LLM Eval Toolkit](https://github.com/abpandey-dev/llm-eval-toolkit)**: test LLM apps the way an SDET tests software. YAML test suites, deterministic assertions plus LLM-as-judge, and CI gates on pass rate.

## 🚀 What I'm working on

- 🤖 Building **LLM-powered apps**: RAG, agents and tool use
- 🧪 Applying my QA background to **AI evals**, so models are measured, not just demoed
- ⚙️ Using AI to **automate testing**: test generation, failure analysis and reporting
- 📚 Learning Machine Learning, Deep Learning, Generative AI and System Design: **Data Science & ML at Scaler**

## 🗺️ Project roadmap

New profile, building in public. Projects will be linked here as they ship:

- [x] **[LLM Eval Toolkit](https://github.com/abpandey-dev/llm-eval-toolkit)**: automated test suites for LLM apps (accuracy, hallucination and regression checks), built the way an SDET would build them · *v0.1 shipped*
- [x] **[NOC Copilot](https://github.com/abpandey-dev/noc-copilot)**: agentic root-cause analysis for 5G network operations, benchmarked against ground truth · *v0.1 shipped*
- [x] **NOC Copilot v0.2**: hard benchmark with multi-fault incidents, cascading failures and maintenance decoys, plus a prompt ablation · *shipped*
- [x] **NOC Copilot v0.3**: messy-telemetry benchmark with alarm storms, missing KPIs, staggered fault start times and busy-hour masking · *shipped*
- [x] **[Telco Churn Copilot](https://github.com/abpandey-dev/telco-churn-copilot)**: churn ML + RAG over policies + LLM copilot with citation checks, executed notebook and retrieval eval in CI · *v0.1 shipped*
- [x] **[Agent Memory Engine](https://github.com/abpandey-dev/agent-memory-engine)**: long-term agent memory with history, hybrid graph + keyword recall, an MCP server and a benchmark against full-context and RAG · *v0.1 shipped*
- [x] **[Rail Punctuality](https://github.com/abpandey-dev/rail-punctuality)**: real-world data project on 136 Indian long-distance trains: polite collector, validated dataset, punctuality findings and charts · *v0.1 shipped*
- [x] **[Netflix Insights](https://github.com/abpandey-dev/netflix-insights)**: official Netflix viewing data + IMDb: directors, genres, decay, country taste and tested recommenders · *v0.1 shipped*
- [x] **[Jio vs Airtel](https://github.com/abpandey-dev/telecom-india)**: verified TRAI subscriber data, M2M-corrected market share, tariff-shock and circle analysis, plus a Claude "ask the data" assistant with a number check · *v0.2 shipped*
- [x] **[Context Compressor](https://github.com/abpandey-dev/context-compressor)**: token compression for tool outputs (lossless JSON tables, log patterns, BM25 select) with a 53-question accuracy benchmark on Claude · *v0.1 shipped*
- [ ] **Agent Memory Engine v0.2**: dense-embedding recall and a run on the public LongMemEval benchmark
- [ ] **NOC Copilot v0.4**: scale test with thousands of cells and multi-hour windows, where tool output no longer fits in one context

## 🛠️ Tech stack

**AI & Data**
![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-FF6F00?style=flat&logo=scikitlearn&logoColor=white)
![Generative AI](https://img.shields.io/badge/Generative%20AI-8A2BE2?style=flat&logo=openai&logoColor=white)
![LLMs](https://img.shields.io/badge/LLMs-111827?style=flat)
![RAG](https://img.shields.io/badge/RAG-7C3AED?style=flat)
![Prompt Engineering](https://img.shields.io/badge/Prompt%20Engineering-0EA5E9?style=flat)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=flat&logo=postgresql&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikitlearn&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white)
![MCP](https://img.shields.io/badge/MCP-6E56CF?style=flat)
![AI Agents](https://img.shields.io/badge/AI%20Agents-D97757?style=flat&logo=anthropic&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=flat&logo=sqlite&logoColor=white)

**Big Data & Cloud**
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazonwebservices&logoColor=white)
![Amazon EMR](https://img.shields.io/badge/EMR-FF9900?style=flat&logo=amazonaws&logoColor=white)
![Athena](https://img.shields.io/badge/Athena-8C4FFF?style=flat&logo=amazonaws&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat&logo=apachekafka&logoColor=white)
![Airflow](https://img.shields.io/badge/Airflow-017CEE?style=flat&logo=apacheairflow&logoColor=white)
![NiFi](https://img.shields.io/badge/NiFi-728E9B?style=flat&logo=apache&logoColor=white)
![OpenSearch](https://img.shields.io/badge/OpenSearch-005EB8?style=flat&logo=opensearch&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?style=flat&logo=grafana&logoColor=white)

**Test Automation**
![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=flat&logo=selenium&logoColor=white)
![Appium](https://img.shields.io/badge/Appium-662D91?style=flat&logo=appium&logoColor=white)
![PyTest](https://img.shields.io/badge/PyTest-0A9EDC?style=flat&logo=pytest&logoColor=white)
![Rest Assured](https://img.shields.io/badge/Rest%20Assured-2E7D32?style=flat)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=flat&logo=postman&logoColor=white)
![TestNG](https://img.shields.io/badge/TestNG-CD3333?style=flat)
![JMeter](https://img.shields.io/badge/JMeter-D22128?style=flat&logo=apachejmeter&logoColor=white)

**Languages & Tooling**
![Java](https://img.shields.io/badge/Java-ED8B00?style=flat&logo=openjdk&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=flat&logo=apachemaven&logoColor=white)
![Jenkins](https://img.shields.io/badge/Jenkins-D24939?style=flat&logo=jenkins&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=flat&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)

## 💼 Experience highlights

- **Big Data Testing** *(Deutsche Telekom Digital Labs)*: pipelines on AWS (EMR, Athena), Kafka, Airflow and NiFi, with monitoring in OpenSearch and Grafana
- **Automation Testing**: web and mobile (Android) with Selenium and Appium; cut manual regression on a personal-loan app by **35%**
- **API Testing**: Rest Assured and Postman; delivered a **100% successful API migration** (EIT → Pennant)
- **Database Testing**: SQL-based data validation
- **CI/CD**: Java, TestNG, Maven and Jenkins
- **Fintech domain**: lending products (CAPP, Joint Lending with DBS Bank, **15+ critical defects** caught pre-production), Zephyr test management

## 📜 Certifications & learning

- Data Science & Machine Learning: **Scaler** *(pursuing)*
- Supervised Machine Learning: **Stanford Online**
- Data Analysis: **IBM**

## 🎯 Goals

- Grow as an **AI Engineer** and ship AI products that make an impact
- Learn continuously and build in public
- *Discipline today, a better tomorrow* 💪

## 📫 Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Abhishek%20Pandey-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/abpandey-ai/)

📍 Gurugram, India · Hybrid work, global impact

---

<sub>*Plan → Learn → Code → Improve → Repeat* 🔁</sub>
