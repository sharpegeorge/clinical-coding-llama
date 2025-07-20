# clinical-coding-llama

### Overview

This project combines a large language model (LLaMA-3) with a Binary Decision Tree (BDT) to perform zero-shot clinical coding from hospital discharge summaries. Each decision point in the tree maps to a yes/no question derived from official ICD-10 coding guidelines, enabling structured and interpretable traversal toward the correct primary diagnosis code. The pipeline is optimized for high-frequency codes and supports transparent, auditable predictions in clinical NLP workflows.

### Features

- Zero-shot ICD-10 code assignment using LLaMA-3 on clinical discharge summaries
- Binary Decision Tree framework guided by official coding guidelines for structured prompt generation
- Interpretable prediction pipeline with traceable yes/no decisions at each node
- Domain-specific preprocessing focused on top 50 most common ICD codes
- Combines LLM reasoning with rule-based decision logic for scalable, auditable clinical NLP

### Datasets

For this project you need access to three datasets which are combined and preprocessed in the file preprocessing.ipynb.
To access these three, you need to gain credentialed access through physionet.org

```
https://physionet.org/content/labelled-notes-hospital-course/1.2.0/
https://physionet.org/content/mimic-iv-note/2.2/note/
https://physionet.org/content/mimiciv/2.2/
```

CITI Data or Specimens Only Research training is required
```
https://physionet.org/content/mimiciv/view-required-training/2.2/#1
```

### Other prerequesites

To run the program, you will also need to gain access to Meta's Llama models through HuggingFace.co

```
https://huggingface.co/meta-llama/Llama-3.1-8B-Instruct
https://huggingface.co/meta-llama/Llama-3.2-3B
```

No training is required, but you will need to request access and have an account set up with a User Access Token
```
https://huggingface.co/docs/hub/en/security-tokens
```

The program is set to run through access with Google Drive using Google Colab, however, can be modified to run elsewhere.

### How to run
1. Clone the repository
   ```bash
   git clone https://github.com/sharpegeorge/clinical-coding-llama.git
   cd clinical-coding-llama
   ```

2. Install dependencies
   ```bash
   pip install -r requirements.txt
   ```

3. Create a data folder in the repository and move the 3 following files there from each dataset as described
   ```bash
   discharge.csv # From MIMIC-Note
   diagnoses_icd.csv # From MIMIC 2.2
   mimic-iv-bhc.csv # From MIMIC-Ext-BHC
   ```

4. Run preprocessing.ipynb
   ```bash
   jupyter notebook preprocessing.ipynb
   ```

5. Run llama.ipynb and/or baseline.ipynb
   ```bash
   jupyter notebook llama.ipynb
   ```

6. Run analysis.ipynb
   ```bash
   jupyter notebook analysis.ipynb
   ```
   
### Files Included
- `src`
    - `analysis.ipynb`
    - `baseline.ipynb`
    - `llama.ipynb`
    - `preprocessing.ipynb`
- `requirements.txt`
