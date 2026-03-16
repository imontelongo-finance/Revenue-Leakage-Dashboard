🕵️‍♂️ Revenue Hunter: Forensic Audit & Risk Engine
A "Finance 4.0" automation tool designed to identify revenue leakage, price-escalation non-compliance, and FX exposure across global entities.

🚀 The Business Problem
In global organizations with multiple billing entities (e.g., Chicago, Berlin, Krakow), manual oversight often leads to:

Missed Price Escalations: Contractual 5% annual increases aren't applied correctly in the ERP.

SLA Leakage: Penalties are applied incorrectly due to uptime variances.

FX Masking: Favorable currency movements hide underlying margin erosion.

🛠️ The Tech Stack
Python (Pandas): The core forensic engine used for data normalization and audit logic.

JSON/Config Management: Decoupled business rules (FX rates, SLA thresholds) from code logic.

React (v0.dev): A high-fidelity executive dashboard fetching live JSON data via GitHub Gists.

GitHub Actions/Gists: Automated data pipeline for real-time reporting.

📊 Core Features
1. Forensic Audit Engine
The system performs a line-by-line audit of billing_export.csv against config.json rules. It calculates the "Contractual Truth" vs. the actual amount billed, isolating Price Leakage from FX Impact.

2. "What-If" Stress Test
A predictive module that simulates a 10% currency devaluation across non-base currencies (BRL, JPY, PLN). This quantifies the "Tail Risk" for the Treasury team.

3. Account-Level Intelligence
Groups data by specific customers (e.g., Siemens AG, N26, Boeing) to identify if leakage is concentrated in Enterprise vs. SMB segments.

📁 Project Structure
auditor.py: The "Brain." Processes raw data and exports JSON insights.

generate_data.py: Creates 24 months of mock billing data with randomized leakage patterns.

config.json: The "Control Center" for FX rates and contract terms.

dashboard_data.json: The processed output used to power the UI.

🏃‍♂️ How to Run
Clone the Repo:

Bash
git clone https://github.com/your-username/Revenue-Hunter.git
Install Dependencies:

Bash
pip install pandas python-dotenv
Execute the Audit:

Bash
python generate_data.py && python auditor.py
