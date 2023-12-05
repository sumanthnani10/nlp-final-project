# NLPositionality

## Project
This is the project repository for the NLPositionality project - Final Project for CS 678.

## Team
- Sumanth Bejugam
- Soumya Thalapaneni
- Sai Hruthik Bojja

## Paper - Referred
__NLPositionality: Characterizing Design Biases of Datasets and Models__
Sebastin Santy, Jenny T. Liang, Ronan Le Bras, Katharina Reinecke, Maarten Sap
_ACL 2023_

## Dataset
For each task, we have two versions of datasets: 
* **original**: original dataset.
* **multilinguality**: dataset with 7 other languages.
* **robustness**: noise inroduces original dataset.

### Format

#### Social Acceptability
| Column Name | Description |
| :--- | :---- | 
| action | An action from the [Social Chemistry](https://maxwellforbes.com/social-chemistry/) dataset. | 
| situation* | The situation corresponding to the action, as determined by the [Social Chemistry](https://maxwellforbes.com/social-chemistry/) dataset. | 
| session_id | The [LabintheWild](https://labinthewild.org) annotator's unique session ID. |
| litw | The [LabintheWild](https://labinthewild.org) annotator's annotation for the action {-2, -1, 0, 1, 2}. |
| socialchem | The mean of the [Social Chemistry](https://maxwellforbes.com/social-chemistry/) annotator's labels of the action (between -2 and 2). |
| delphi | The [Delphi](https://delphi.allenai.org/) model's prediction of the action {-1, 0, 1}.|
| gpt4 | The [GPT-4](https://openai.com/gpt-4) model's prediction of the action {-1, 0, 1}. |
| age | The age of the [LabintheWild](https://labinthewild.org) annotator. |
| gender | The gender of the [LabintheWild](https://labinthewild.org) annotator. |
| ethnicity | The ethnicity of the [LabintheWild](https://labinthewild.org) annotator. If there are multiple ethnicities, there are multiple entries for the user. |
| religion | Religion the [LabintheWild](https://labinthewild.org) annotator practices. |
| education | The highest level of education the [LabintheWild](https://labinthewild.org) annotator attained. |
| country_longest | The country the [LabintheWild](https://labinthewild.org) annotator lived in the longest. |
| country_residence | The country the [LabintheWild](https://labinthewild.org) annotator currently lives in. |
| native_language | The native language of the [LabintheWild](https://labinthewild.org) annotator. |

#### Hate Speech & Toxicity
| Column Name | Description |
| :--- | :---- | 
| action | An instance from the [Dynahate](https://aclanthology.org/2021.acl-long.132.pdf) dataset. | 
| session_id | The [LabintheWild](https://labinthewild.org) annotator's unique session ID. |
| litw | The [LabintheWild](https://labinthewild.org) annotator's annotation for the action {-1, 0, 1}. |
| dynahate | The [Dynahate](https://aclanthology.org/2021.acl-long.132.pdf) annotator's label of the action {0, 1}. |
| perspective | The [Perspective API](https://perspectiveapi.com/) model's prediction of the action (between 0 and 1).|
| rewire | The [Rewire API](https://rewire.online/rewire-api-access/) model's prediction of the action (between 0 and 1).|
| hateroberta | The [ToxiGen RoBERTa](https://aclanthology.org/2022.acl-long.234.pdf) model's prediction of the action (between 0 and 1).|
| gpt4 | The [GPT-4](https://openai.com/gpt-4) model's prediction of the action {0, 1}. |
| age | The age of the [LabintheWild](https://labinthewild.org) annotator. |
| gender | The gender of the [LabintheWild](https://labinthewild.org) annotator. |
| ethnicity | The ethnicity of the [LabintheWild](https://labinthewild.org) annotator. If there are multiple ethnicities, there are multiple entries for the user. |
| religion | Religion the [LabintheWild](https://labinthewild.org) annotator practices. |
| education | The highest level of education the [LabintheWild](https://labinthewild.org) annotator attained. |
| country_longest | The country the [LabintheWild](https://labinthewild.org) annotator lived in the longest. |
| country_residence | The country the [LabintheWild](https://labinthewild.org) annotator currently lives in. |
| native_language | The native language of the [LabintheWild](https://labinthewild.org) annotator. |

#### For Multilinguality (Extra Columns)
| Column Name | Description |
| :--- | :---- | 
| original | Action column in english from original dataset. |
| lang | Language of the translated action. |

#### For Robustness (Extra Columns)
| Column Name | Description |
| :--- | :---- | 
| original | Action column in english from original dataset. |

## Code
To replicate our analyses, please follow these steps:
1. **Clone this repository**.
2. **Run `final-project.ipynb`**.

## Tour


### Installation and Dependencies

- Install and import all the required packages, including google-api-python-client, openai, etc.

### Dataset Preprocessing
- Translate the dataset into seven other languages using the googletrans module to introduce multilinguality using [translate.py](translate.ipynb).
- Add noise to the dataset using the nlpaug module to introduce robustness [augment.py](augment.ipynb).

### Analysis

- Calculate values for the Perspective, RoBERTa, and GPT-4 models on the Toxicity dataset for both translated and augmented versions.

- Calculate GPT-4 values on the Social Acceptability dataset for both translated and augmented versions.

- Run [final-project.ipynb](final_project.ipynb) to acheive that
