# Reusable GitHub Actions Workflow (Basic Addition)

##  Overview
This project demonstrates how to create **Reusable Workflows** in GitHub Actions. It consists of two workflows: a "Caller" workflow that triggers the action and passes data, and a "Called" (reusable) workflow that receives the data and executes a script. 

This modular approach is a CI/CD best practice to keep pipelines clean and avoid repeating code.

## ⚙️ How It Works

### 1. The Calling Workflow (`calling-workflow.yml`)
* **Trigger:** Manually triggered using `workflow_dispatch`.
* **Action:** It acts purely as a trigger. Instead of running its own steps, it uses the `uses` keyword to call the reusable workflow located in the `SyedShakirX/test.py` repository.
* **Data Passed:** It passes two input parameters (`num1: 111` and `num2: 222`) to the called workflow.

### 2. The Called Workflow (`called-workflow.yml`)
* **Trigger:** Can be triggered either by another workflow (`workflow_call`) or manually (`workflow_dispatch`).
* **Inputs Required:** Expects two numerical inputs (`num1` and `num2`).
* **Action:** Runs a single job on an `ubuntu-slim` runner that takes the two input numbers, adds them together using a simple bash script, and prints the result to the console.

##  How to Run
1. Go to the **Actions** tab in this GitHub repository.
2. Select **This is Calling Workflow** from the left sidebar.
3. Click **Run workflow**.
4. Click on the completed workflow run to view the logs and see the calculated output of the two numbers!
