<div align="center">

<a href="https://github.com/Kaif10">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24&height=200&section=header&text=Kaif%20Kohari&fontSize=60&fontColor=ffffff&animation=fadeIn&fontAlignY=38&desc=Machine%20Learning%20Engineer%20%E2%80%A2%20London,%20UK&descAlignY=58&descSize=18" alt="header" />
</a>

### Translating cutting-edge research into production AI

<br/>

<p>
  <a href="https://www.linkedin.com/in/kaif-kohari-a34433190/">
    <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/>
  </a>
  <a href="https://medium.com/@kaifkohari10">
    <img src="https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white" alt="Medium"/>
  </a>
  <a href="https://my-elegant-space.lovable.app/">
    <img src="https://img.shields.io/badge/Portfolio-1f6feb?style=for-the-badge&logo=safari&logoColor=white" alt="Portfolio"/>
  </a>
  <a href="mailto:kaifkohari10@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/>
  </a>
</p>

<img src="https://komarev.com/ghpvc/?username=Kaif10&style=flat-square&color=4F8CFF&label=Profile+Views" alt="Profile Views"/>
<img src="https://img.shields.io/github/followers/Kaif10?label=Followers&style=flat-square&color=4F8CFF" alt="Followers"/>

<br/>

<table>
<tr>
<td>
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=17&pause=1200&color=00E676&center=true&vCenter=true&width=540&height=40&lines=%F0%9F%9F%A2+Currently+%40+London+Export+Corporation;%F0%9F%A4%96+Building+industrial-scale+multi-agent+systems" alt="current status" />
</td>
</tr>
</table>

</div>

---

## 🧠 &nbsp;About Me

<img align="right" width="35%" src="https://raw.githubusercontent.com/abhisheknaiidu/abhisheknaiidu/master/code.gif" alt="coding gif"/>


🔭 &nbsp;**Machine Learning Engineer** based in **London** — currently building **Industrial-scale multi-agent systems @ London Export Corporation**.

🧪 &nbsp;Often the **founding ML engineer** at growing teams, owning the full path from research to deployed, monitored infrastructure.

🎓 &nbsp; **Masters in Applied Data Science** @ University of London *(Distinction)*

⚡ &nbsp;Deep interest in **LLM Reasoning**, **Multi-Agent Systems**, **Low-Latency Inference**, and **Reinforcement Learning**.

🤝 &nbsp;Passionate about **open source** and writing about ML on [Medium](https://medium.com/@kaifkohari10).

💬 &nbsp;Ask me about **PyTorch, LangChain, vector retrieval, or anything LLM-flavoured**.

<br clear="right"/>

---

## 🌍 &nbsp;Open-Source Contributions

<div align="center">

**11 merged fixes** across **9 repositories** · **400k+** combined stars
<sub>Real correctness bugs — schema corruption, a security vulnerability, silent training-time no-ops — each reviewed and merged by maintainers.</sub>

</div>

| | Project | Merged fixes |
|:--:|---|---|
| 🧠 | **OpenAI** · `openai-agents-python` <sub>28k★</sub> | [#4036](https://github.com/openai/openai-agents-python/pull/4036) tool-schema corruption · [#4089](https://github.com/openai/openai-agents-python/pull/4089) cross-turn reasoning leak · [#4090](https://github.com/openai/openai-agents-python/pull/4090) guardrail reporting |
| 🤗 | **Hugging Face** · `datasets` <sub>22k★</sub> | [#8325](https://github.com/huggingface/datasets/pull/8325) path-traversal vulnerability *(CWE-22)* |
| 🧩 | **Hugging Face** · `peft` <sub>21k★</sub> | [#3503](https://github.com/huggingface/peft/pull/3503) LoRA+ embedding learning rate never applied |
| 🔎 | **Hugging Face** · `sentence-transformers` <sub>19k★</sub> | [#3880](https://github.com/huggingface/sentence-transformers/pull/3880) gradient leak in distillation loss |
| 🔶 | **Keras** <sub>64k★</sub> | [#23375](https://github.com/keras-team/keras/pull/23375) layer config dropped `sparse` on reload |
| 🎯 | `outlines` <sub>15k★</sub> | [#1967](https://github.com/dottxt-ai/outlines/pull/1967) Gemini system-instruction handling |
| 🧮 | `TheAlgorithms/Python` <sub>223k★</sub> | [#2219](https://github.com/TheAlgorithms/Python/pull/2219) job-scraping module — still shipping 5 years on |
| ⚙️ | `statsmodels` | [#9908](https://github.com/statsmodels/statsmodels/pull/9908) optimizer Hessian handling · [#9909](https://github.com/statsmodels/statsmodels/pull/9909) sparse multinomial CI |
| 📈 | `yfinance` | [#2897](https://github.com/ranaroussi/yfinance/pull/2897) dividend-repair crash |

<details>
<summary><sub><b>What each fix actually did →</b></sub></summary>

<br/>

**OpenAI · `openai-agents-python`**
- **#4036** — the tool-output schema trimmer recursed into `properties` treating *parameter names* as schema keywords, deleting any parameter called `description`/`title`/`examples` while leaving it in `required`. The model received an invalid schema with hidden parameters.
- **#4089** — a reasoning item not immediately followed by its assistant message kept its signed thinking blocks pending, so a previous turn's private reasoning was replayed on a later turn.
- **#4090** — output guardrail results were discarded when a tripwire aborted the run, mirroring a fix the maintainers had just landed for input guardrails.

**Hugging Face · `datasets` — #8325**
An unsanitized `file_name` in dataset metadata allowed arbitrary file reads (CWE-22). The fix covers absolute paths, `..` traversal, fsspec chained URLs (`zip://…::…`) and symlink escapes.

**Hugging Face · `peft` — #3503**
LoRA+'s `loraplus_lr_embedding` had been a silent no-op since 2024: the code resolved a *parameter* where it needed the owning *module*, so the embedding parameter group was always empty and embedding LoRA weights trained at the base learning rate, missing the B-matrix boost that LoRA+ exists to provide.

**Hugging Face · `sentence-transformers` — #3880**
In `AdaptiveLayerLoss`, the KL-divergence teacher was never detached, so gradients flowed back into the final layer — pulling the teacher toward the students. A bracketing error also scaled the per-layer loss by a factor of `N²`.

**Keras — #23375**
`CategoryEncoding.get_config()` omitted `sparse`, so a model saved with `sparse=True` silently reloaded dense. Every sibling preprocessing layer already serialized it.

**`outlines` — #1967**
Gemini's `Content.role` accepts only `user`/`model`, but the adapter passed `system` straight through, malforming every chat with a system message. System messages are now collected — wherever they appear — and passed as `system_instruction`.

</details>

---

## 🛠️ &nbsp;Tech Stack

<div align="center">

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=postgresql&logoColor=white)

**ML / Deep Learning**

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=for-the-badge&logo=pytorch&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Hugging Face](https://img.shields.io/badge/%F0%9F%A4%97_Hugging_Face-FFD21E?style=for-the-badge&logoColor=black)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)

**LLM / Agentic**

![PydanticAI](https://img.shields.io/badge/PydanticAI-E92063?style=for-the-badge&logo=pydantic&logoColor=white)
![LangGraph](https://img.shields.io/badge/LangGraph-1C3C3C?style=for-the-badge&logo=langchain&logoColor=white)
![RAG](https://img.shields.io/badge/RAG-FF6F61?style=for-the-badge&logo=databricks&logoColor=white)


**Data & Pipelines**

![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Spark](https://img.shields.io/badge/Apache_Spark-E25A1C?style=for-the-badge&logo=apachespark&logoColor=white)
![Airflow](https://img.shields.io/badge/Airflow-017CEE?style=for-the-badge&logo=apacheairflow&logoColor=white)
![Polars](https://img.shields.io/badge/Polars-CD792C?style=for-the-badge&logo=polars&logoColor=white)

**Backend & MLOps**

![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

</div>

---

## 📈 &nbsp;GitHub Stats

<div align="center">

<img height="170" src="https://github-readme-stats.vercel.app/api?username=Kaif10&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=4F8CFF&icon_color=4F8CFF&text_color=c9d1d9&include_all_commits=true&count_private=true" alt="GitHub Stats"/>
<img height="170" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Kaif10&layout=compact&theme=tokyonight&hide_border=true&bg_color=0D1117&title_color=4F8CFF&text_color=c9d1d9&langs_count=8" alt="Top Languages"/>

<br/><br/>

<img src="https://streak-stats.demolab.com?user=Kaif10&theme=tokyonight&hide_border=true&background=0D1117&stroke=4F8CFF&ring=4F8CFF&fire=FF6B6B&currStreakLabel=4F8CFF" alt="GitHub Streak"/>

</div>

### 🐍 Contribution Graph

<div align="center">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/Kaif10/Kaif10/output/github-contribution-grid-snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/Kaif10/Kaif10/output/github-contribution-grid-snake.svg" />
  <img alt="snake animation" src="https://raw.githubusercontent.com/Kaif10/Kaif10/output/github-contribution-grid-snake.svg" />
</picture>

</div>

---

## ✍️ &nbsp;Latest from Medium

<!-- BLOG-POST-LIST:START -->
<!-- BLOG-POST-LIST:END -->

> 📝 &nbsp;Check out my [Medium](https://medium.com/@kaifkohari10) for deep-dives on ML, LLMs, and production AI.

---

## 🤝 &nbsp;Let's Connect

<div align="center">

I'm always up for a chat about **LLM reasoning, multi-agent systems, low-latency ML, or applying ML in financial markets** — drop me a line.

<a href="mailto:kaifkohari10@gmail.com">
  <img src="https://img.shields.io/badge/Reach_out-Send_an_email-4F8CFF?style=for-the-badge&logo=minutemailer&logoColor=white" alt="Email me"/>
</a>

<br/><br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=12,20,24&height=120&section=footer" alt="footer"/>

</div>
