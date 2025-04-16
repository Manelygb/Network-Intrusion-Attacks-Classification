
# Enhancing WLAN Security Using Artificial Intelligence

This repository contains the full implementation of AI-based models developed to detect various WLAN attacks as part of the ENSIA project for the **Wireless Communication Networks and Systems** module.

The system combines machine learning techniques with real network traffic data to detect and mitigate attacks such as:

- Deauthentication
- ARP Spoofing
- Rogue Access Points
- WPA2 Key Cracking (approximated using proxy modeling)
- DDoS attacks (Layer 3/4)

Each notebook treats a dataset that corresponds to one or more of the attacks. The repository includes dataset preprocessing, model training, evaluation, and supporting analysis.

---

## 📁 Repository Structure

```
📂 notebooks/
├── AWID_Multiclass_Model.ipynb
├── AWID_Scapy_Model.ipynb
├── ARP_Kaggle_Model.ipynb
├── WPA2_Cracking_Proxy_Model.ipynb
├── DDoS_Zeek_Model.ipynb
📂 data/
└── [Place downloaded datasets here]
README.md
```

---

## 📚 Notebooks Overview

### 1. `AWID_Multiclass_Model.ipynb`
- **Goal:** Detect multiple WLAN attacks (Deauth, Rogue AP, Website Spoofing) from the AWID dataset.
- **Dataset:** [AWID Dataset](https://icsdweb.aegean.gr/awid/awid3)
- **Highlights:**
  - Reduced from 254 to 23 key features.
  - Trained with Random Forest.
  - Accuracy: 99.87%, F1-Score: ~1.00

---

### 2. `AWID_Scapy_Model.ipynb`
- **Goal:** Create a reduced model using only Scapy-compatible features for real-time packet capture.
- **Dataset:** AWID Dataset
- **Highlights:**
  - Used only 9 features available via Scapy.
  - Imputation and light preprocessing.
  - Accuracy: 99%, F1-Score: 0.9835

---

### 3. `ARP_Kaggle_Model.ipynb`
- **Goal:** Detect ARP spoofing using a smaller, balanced dataset.
- **Dataset:** [ARP Spoofing Dataset on Kaggle](https://www.kaggle.com/datasets/mizanunswcyber/arp-spoofing-based-mitm-attack-dataset)
- **Highlights:**
  - Binary classification.
  - Fast training and clear ARP traffic patterns.
  - Accuracy: 94.7%, F1-Score: 0.95

---

### 4. `WPA2_Cracking_Proxy_Model.ipynb`
- **Goal:** Approximate WPA2 cracking detection using brute-force behavior as a proxy.
- **Dataset:** [CSE-CIC-IDS2018 Cleaned](https://www.kaggle.com/datasets/ekkykharismadhany/csecicids2018-cleaned)
- **Highlights:**
  - Modeled based on repeated handshake patterns.
  - Feature approximation mapped to attack structure.
  - Accuracy: 99.99%

---

### 5. `DDoS_Zeek_Model.ipynb`
- **Goal:** Detect DDoS attacks using Zeek-based flow features.
- **Dataset:** [CIC-IDS2017](https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset)
- **Highlights:**
  - Used features like flow duration, total packets.
  - Designed for real-time detection via Zeek logs.
  - Accuracy: 100%, F1-Score: 0.9996

---

## 🧠 Project Notes

- Models were selected based on interpretability, performance, and real-time compatibility.
- All models use the Random Forest algorithm for fast and accurate classification.
- Separate models were created for full dataset training and live-capture scenarios.

