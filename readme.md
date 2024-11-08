# SDRL Tracker: Subcontract Data Requirements List Management

Hello, this is my program designed to simulate a live environment and help you organize and track SDRLs or any other contract details you may need to store for quick access and presentation.

## Overview
The SDRL Tracker is a Python tool that helps contract managers manage, track, and report on SDRLs (Subcontract Data Requirements Lists). It generates sample SDRL entries, stores them in an SQLite database, and provides ways to monitor deadlines, prioritize tasks, and export reports.

## Features
- **Generate Fake SDRLs**: Creates SDRLs with ID, description, due date, responsible party, status, and priority.
- **Database Storage**: Uses SQLite for efficient data storage.
- **Priority & Due Date Tracking**: Sorts SDRLs by due date and priority.
- **Export Reports**: Generates CSV reports for analysis.

## Technologies Used
- Python 3.12
- SQLite for data storage
- Faker for generating sample SDRLs
- Pandas for data manipulation

## Installation
1. Clone the repository:

```bash
git clone https://github.com/yourusername/sdrl-tracker.git
cd sdrl-tracker
```

2. Create a virtual environment:
   
```bash
python -m venv env
#Activate the environment:
#macOS/Linux:
source env/bin/activate
#Windows:
.\env\Scripts\activate
#Install dependencies:
pip install -r requirements.txt
```

# Usage

1. Generate SDRLs: Run the main script to populate the database with sample SDRLs.

```bash
from src.sdrl_tracker import generate_fake_sdrls, insert_sdrls_to_db
# Generate 100 SDRLs
sdrls = generate_fake_sdrls(100) 
# Insert SDRLs into the DB
insert_sdrls_to_db(sdrls)
```         

1. Insert SDRLs: Populate the database with sample SDRLs.

    ```python
    from src.sdrl_tracker import generate_fake_sdrls, insert_sdrls_to_db
    # Generate 100 SDRLs
    sdrls = generate_fake_sdrls(100)
    # Insert SDRLs into the DB
    insert_sdrls_to_db(sdrls)
    ```
    
2. Query SDRLs: Retrieve and filter SDRLs by due date or priority.

    ```python
    from src.sdrl_tracker import get_upcoming_sdrls

    # Get upcoming SDRLs due in the next 30 days
    upcoming_sdrls = get_upcoming_sdrls(days=30)
    for sdrl in upcoming_sdrls:
        print(f"SDRL ID: {sdrl.sdrl_id}, Due Date: {sdrl.due_date}, Priority: {sdrl.priority}")
    ```
    
3. Export to CSV: Generate a CSV report of all SDRLs.

    ```python
    from src.sdrl_tracker import export_sdrl_report
    # Export SDRL data to a CSV file
    export_sdrl_report()
    ```

4. # Example Output

```plaintext
SDRL ID: 123e4567-e89b-12d3-a456-426614174000, Due Date: 2024-11-15, Priority: High, Status: In Progress
SDRL ID: 789e4567-e89b-12d3-a456-426614174111, Due Date: 2024-12-01, Priority: Medium, Status: Not Started
```

# Contributing 

Contributions are welcome! If you have suggestions for improvements or new features, please feel free to open an issue or submit a pull request.

# License

This project is licensed under the MIT License. See the LICENSE file for details.

# Contact

Created by Thomas Galarneau (https://github.com/hamiltonius) – feel free to reach out with questions or feedback.     
