# TeleQnA 

## Introduction

TeleQnA is a comprehensive dataset tailored to assess the knowledge of Large Language Models (LLMs) in the field of telecommunications. It encompasses 10,000 multiple-choice questions distributed across five distinct categories:

- **Lexicon:** This category comprises 500 questions that delve into the realm of general telecom terminology and definitions.

- **Research overview:** Comprising 2,000 questions, this category provides a broad overview of telecom research, spanning a wide spectrum of telecom-related topics.

- **Research publications:** With 4,500 questions, this category contains detailed inquiries regarding multi-disciplanary research in telecommunications, drawing from a variety of sources such as transactions and conferences proceedings.

- **Standards overview:** This category consists of 1,000 questions related to summaries of standards from multiple standarization bodies like 3GPP and IEEE.

- **Standards specification:** With 2,000 questions, this category explores the technical specifications and practical implementations of telecommunications systems, leveraging information from standardization bodies like 3GPP and IEEE.


## Dataset Format

Each question is represented in JSON format, comprising five distinct fields:

- **Question:** This field consists of a string that presents the question associated with a specific concept within the telecommunications domain.

- **Options:** This field comprises a set of strings representing the various answer options.

- **Answer:** This field contains a string that adheres to the format ’option ID: Answer’ and presents the correct response to the question. A single option is correct; however, options may include choices like “All of the Above” or “Both options 1 and 2”.

- **Explanation:** This field encompasses a string that clarifies the reasoning behind the correct answer.

- **Category:** This field includes a label identifying the source category (e.g., Lexicon, research overview, etc.).

## Dataset Instance 

An example of the dataset is provided below:

```
question 2045: {
		"question": "What is the maximum number of eigenmodes that the MIMO channel can support? 
                (nt is the number of transmit antennas, nr is the number of receive antennas)",
		"option 1": "nt",
		"option 2": "nr",
		"option 3": "min(nt, nr)",
		"option 4": "max(nt, nr)",
		"answer": "option 3: min(nt, nr)",
		"explanation": "The maximum number of eigenmodes that the MIMO channel can support 
		is min(nt, nr).",
		"category": "Research publications"
                } 
```


## Experiments Code

The provided code allows to evaluate the performance of OpenAI's models (e.g., GPT-3.5). To do so, follow the below steps

- Clone the repository
- Install the required dependencies using the following command:

```pip install -r requirements.txt```

- Insert OpenAI's API key into the evaluation_tools script.
- Run the command below

```python run.py``` 

Upon completion, a .txt file in JSON format is generated. This file contains the original dataset, with two additional fields added to each question:

- **tested answer:** This field contains the answer chosen by the tested model.

- **correct:** This field is marked as "True" when the tested answer matches the designated correct answer in the dataset.

# Citation 

If you would like to use the data or code, please cite the paper:

```
@misc{maatouk2023teleqna,
      title={TeleQnA: A Benchmark Dataset to Assess Large Language Models Telecommunications Knowledge}, 
      author={Ali Maatouk and Fadhel Ayed and Nicola Piovesan and Antonio De Domenico and Merouane Debbah and Zhi-Quan Luo},
      year={2023},
      eprint={2310.15051},
      archivePrefix={arXiv},
      primaryClass={cs.IT}
     }
```
