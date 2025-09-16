# ICIKG: Industrial Chain Knowledge Graph Dataset

ICIKG is an open-source dataset focused on constructing a temporally-resolved Industrial Chain Knowledge Graph.  
Designed to support research on industrial dependencies, supply–demand relationships, and dynamic risk forecasting, ICIKG provides a comprehensive, temporally-aware representation of industrial chain structures and their evolution.  
This repository includes three datasets:
- **ICIKG**: the full dataset  
- **ICIKG-subset**: a smaller subset for quick experimentation  
- **ICIKG-25**: an extended subset spanning 25 years of data  

---

## Background

While general-purpose knowledge graphs are abundant, domain-specific ones remain rare, particularly in the industrial and supply chain sector.  
ICIKG aims to fill this gap by offering a resource that integrates heterogeneous sources such as news, patents, industry reports, and statistical yearbooks, spanning from **2015-01-01 to 2025-09-02**.  
Through processes of entity extraction, disambiguation, and relation alignment, ICIKG delivers a structured foundation for academic research and real-world applications.

---

## ICIKG Dataset

The dataset captures **entities** (industries, companies, patents), **relations** (e.g., upstream, supply, inclusion), and **temporal annotations** across a ten-year period. ICIKG is built to support temporal knowledge graph tasks and industrial chain analysis. The overall construction workflow of the dataset is illustrated in the figure below.
![Alt text](/overall.png)


---

## Dataset Structure

- Temporal Knowledge Graph (TKG) with event quadruples  
- Quadruples tagged with specific timestamps corresponding to real-world dates  
- Training, validation, and test splits organized chronologically  
- Coverage across a broad range of industrial chain sectors

### Data Format

**ICIKG** is the default dataset folder including the graph dataset and its corresponding data splits. The dataset is organized in the following structure:

* `train.txt`, `valid.txt`, and `test.txt`: The first four columns correspond to **head entity, relation, tail entity, and time ID**.

* `stat.txt`: The first three columns correspond to the **number of entities, number of relations, and number of timestamps**.  


* `entity2id.txt`: Maps entities to IDs.  


* `relation2id.txt`: Maps relations to IDs.  


* `time2id.txt`: Provides mapping from time IDs to real-world dates.  

**ICIKG-subset**: A smaller representative dataset adopting the same format as `/ICIKG`, designed for lightweight testing and experimentation.

---

## Usage

The dataset is designed for temporal knowledge graph methods and graph-based AI research, enabling applications such as:

- Temporal Link Prediction  
- Industrial Chain Dependency Modeling  
- Supply Chain Risk Forecasting  
- Entity and Relation Evolution Analysis  

ICIKG is freely available for academic and research purposes.

---
