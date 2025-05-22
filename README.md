# 🧮 Hadoop MapReduce: Max Stock Price by Symbol

This project uses Hadoop MapReduce and Python to identify the **maximum trade price** per stock from a historical dataset.  
Executed on **AWS EMR** as a real-world distributed data processing task.

---

## 🧠 What This Project Demonstrates

- Writing **custom MapReduce logic** in Python  
- Running jobs on **Amazon EMR cluster**  
- Using HDFS and SSH to manage files  
- Performing distributed analysis with **big data tools**

---

## 📁 Files Included

- [`mapper.py`](mapper.py): Extracts `<symbol>\t<price>` from each line  
- [`reducer.py`](reducer.py): Aggregates values to find max price per symbol  
- [`NYSE_DATA.txt`](NYSE_DATA.txt): Sample dataset used in testing  
- [`aws-emr-job-writeup.pdf`](aws-emr-job-writeup.pdf): Lab summary (optional)  
- [`emr-cluster-preview.png`](emr-cluster-preview.png): Screenshot of job execution  

---

## ⚙️ How to Run on Hadoop

```bash
hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar \
 -input /user/hadoop/NYSE_DATA.txt \
 -output /user/hadoop/output \
 -mapper mapper.py \
 -reducer reducer.py

---

## 📄 Sample Input (`NYSE_DATA.txt`)

CAH,Mon,48  
GE,Tue,12  
MCD,Wed,170  
PFE,Thu,40  
BAC,Fri,26  

---

## 🖥️ Sample Output (from `reducer.py`)

BAC 26
CAH 56
GE 15
MCD 175
PFE 45


---

## 🖼️ Preview

(emr-cluster-preview.png)

> *This image shows the AWS EMR job setup or SSH terminal output during the Hadoop streaming job.*



