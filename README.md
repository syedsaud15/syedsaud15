<div align="center">

<img src="https://raw.githubusercontent.com/syedsaud15/syedsaud15/main/assets/pipeline-banner.svg" width="100%"/>

<br/>

<img src="https://komarev.com/ghpvc/?username=syedsaud15&style=for-the-badge&color=38bdf8&label=PROFILE+VIEWS"/>
<img src="https://img.shields.io/badge/OPEN%20TO%20WORK-22c55e?style=for-the-badge&labelColor=0d1117"/>

</div>

<br/>

## 🧑‍💻 About me

I'm a Data Engineer specializing in **production-grade ETL/ELT pipelines**, **Lakehouse architectures**, and **cloud-native data platforms**. I focus on turning raw, messy data into reliable, business-ready datasets — with an emphasis on scalability, automation, and clean engineering practices.

- 🔭 Building **end-to-end Lakehouse pipelines** on Databricks & Snowflake
- 🌱 Deepening **dbt, Airflow orchestration & data modeling**
- 🤖 Exploring **AI + Data Engineering** — RAG pipelines, vector search
- 📫 **saudhere15@gmail.com**

<br/>

## 🛠️ Tech stack

<div align="center">

<img src="https://skillicons.dev/icons?i=python,mysql,bash,git,github,aws,docker,vscode&theme=dark" />

<br/><br/>

<img src="https://img.shields.io/badge/Apache%20Spark-E25A1C?style=flat-square&logo=apachespark&logoColor=white"/>
<img src="https://img.shields.io/badge/PySpark-E25A1C?style=flat-square&logo=apachespark&logoColor=white"/>
<img src="https://img.shields.io/badge/Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white"/>
<img src="https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=snowflake&logoColor=white"/>
<img src="https://img.shields.io/badge/dbt-FF694B?style=flat-square&logo=dbt&logoColor=white"/>
<img src="https://img.shields.io/badge/Airflow-017CEE?style=flat-square&logo=apacheairflow&logoColor=white"/>
<img src="https://img.shields.io/badge/Power%20BI-F2C811?style=flat-square&logo=powerbi&logoColor=black"/>
<img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white"/>

</div>

<br/>

## 🚀 Featured projects

<table>
<tr>
<td width="50%" valign="top">

**🏭 [FMCG Lakehouse Pipeline](https://github.com/syedsaud15/FMCG-Sales-Analytics-Databricks)**
Production-style pipeline on Databricks using Medallion Architecture (Bronze → Silver → Gold).
`Databricks` `PySpark` `AWS S3` `SQL`

</td>
<td width="50%" valign="top">

**🚖 [Transportation Analytics Platform](https://github.com/syedsaud15/aws-end-to-end-data-engineering-project)**
Analytics solution with incremental processing and business KPI dashboards.
`PySpark` `Databricks` `SQL` `Power BI`

</td>
</tr>
<tr>
<td width="50%" valign="top">

**❄️ [Snowflake + dbt + Airflow Pipeline](https://github.com/syedsaud15/snowflake-projects)**
Complete Modern Data Stack — raw ingestion to tested, scheduled models.
`Snowflake` `dbt` `Airflow` `Python`

</td>
<td width="50%" valign="top">

**📰 [RAG Document Chatbot](https://github.com/syedsaud15/RAG-Document-Chatbot)**
AI research assistant answering questions over documents via RAG.
`LangChain` `ChromaDB` `Gemini` `Streamlit`

</td>
</tr>
</table>

<br/>

## 📊 GitHub analytics

<div align="center">
<img width="49%" src="https://github-readme-stats.vercel.app/api?username=syedsaud15&show_icons=true&theme=tokyonight&hide_border=true&rank_icon=github"/>
<img width="49%" src="https://github-readme-streak-stats.herokuapp.com/?user=syedsaud15&theme=tokyonight&hide_border=true"/>
</div>

<div align="center">
<img src="https://github-profile-trophy.vercel.app/?username=syedsaud15&theme=tokyonight&no-frame=true&row=1&column=7"/>
</div>

<div align="center">
<img src="https://raw.githubusercontent.com/syedsaud15/syedsaud15/output/github-contribution-grid-snake-dark.svg"/>
</div>

<br/>

<div align="center">

## 🤝 Let's connect

<a href="https://www.linkedin.com/in/syed-saud-alam/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
<a href="mailto:saudhere15@gmail.com"><img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white"/></a>
<a href="https://syedsaud15.github.io/syed-saud-portfolio/"><img src="https://img.shields.io/badge/Portfolio-111111?style=for-the-badge&logo=vercel&logoColor=white"/></a>

</div>

name: Generate Snake Animation

on:
  schedule:
    - cron: "0 0 * * *"   # runs once every day
  workflow_dispatch: {}    # allows manual trigger from Actions tab
  push:
    branches:
      - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    steps:
      - name: Generate github-contribution-grid-snake.svg
        uses: Platane/snk@v3
        with:
          github_user_name: syedsaud15
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark

      - name: Push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
