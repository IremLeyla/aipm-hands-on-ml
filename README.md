# Hands on ML for AIPMs

This is a hands-on exercise for AI Product Management students to explore how machine learning models inform product decisions. You play a Product Manager at TeamFlow, a subscription-based SaaS platform, and your goal is to predict which users are likely to churn in the next 30 days so the growth and marketing teams can act early. You will build simple, explainable models on behavioural and subscription data, evaluate them, and reason about the business trade-offs. The dataset is intentionally small and synthetic: the focus is product decision-making and metric trade-offs, not production-grade modelling.

## Learning Objectives

By the end of this repository, you should be able to:

- Train different classification models to predict customer churn.
- Calculate recall, precision, and F1 for each model, and select the metric that fits the business constraints.
- Compare the models and choose the one that best balances performance with explainability.
- Classify prediction errors as false positives or false negatives, and quantify the business cost of each.
- Identify overfitting and underfitting from the gap between training and test performance.
- Recommend whether to ship the model, and justify the decision to a non-technical stakeholder.

## Learning Path

| File / Folder | Description |
|---|---|
| [**01 - Assignment**](01_assignment.md) | The business brief: context, dataset and feature descriptions, and the reflection questions to answer. |
| [**02 - Churn Prediction**](02_churn_prediction.ipynb) | The working notebook where you build and evaluate your churn models. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Data**](data/) | The synthetic customer churn dataset used in the exercise. |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Pinned dependency lock file. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a **placeholder**. Replace it, including the `< >` brackets, with your own value. For example, `cd <repo-name>` becomes `cd aipm-hands-on-ml`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> If you are working in pairs or groups, only **one person** should complete this step.

---

### 2. Add Collaborators (Pairs/Groups Only)

If working with teammates:

1. Open the repository on GitHub
2. Go to **Settings → Collaborators**
3. Add your teammates as collaborators
4. Share the repository link with your team

Teammates should accept the invitation before continuing.

---

### 3. Clone the Repository

Copy the SSH URL from the **Code** button on GitHub, then run:

```bash
git clone <copied-ssh-url>
```

The copied SSH URL will look like `git@github.com:<your-username>/<repo-name>.git`.

---

### 4. Move into the Project Folder and Install Dependencies

This installs all dependencies and creates a virtual environment in (`.venv/`).

```bash
cd <repo-name>
uv sync
```

---

### 5. Open the Notebook

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open `02_churn_prediction.ipynb` and select the Python environment created by `uv sync` as the kernel.

## References & Further Reading

- [scikit-learn: metrics and scoring](https://scikit-learn.org/stable/modules/model_evaluation.html): Official reference for precision, recall, F1, and the confusion matrix.
- [Google ML Crash Course: precision and recall](https://developers.google.com/machine-learning/crash-course/classification/precision-and-recall): A plain-language explanation of the recall versus precision trade-off, with the threshold intuition this exercise relies on.
- [scikit-learn: decision trees](https://scikit-learn.org/stable/modules/tree.html): How decision trees work, including `max_depth` and the explainability strengths and overfitting risks that matter to a PM.
- [scikit-learn: underfitting vs overfitting](https://scikit-learn.org/stable/auto_examples/model_selection/plot_underfitting_overfitting.html): A worked example of the bias-variance trade-off you will frame as product risk.
- [Telco Customer Churn dataset (Kaggle)](https://www.kaggle.com/datasets/blastchar/telco-customer-churn): A real-world churn dataset and community notebooks showing how churn prediction is approached in practice.
