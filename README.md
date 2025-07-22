SFDC Demo Data Generator
A Python script that generates realistic Salesforce (SFDC) customer success and implementation data for demonstration, testing, and training purposes.
Overview
This tool creates synthetic customer account data that mirrors real-world Salesforce implementations, including various implementation stages, health metrics, support tickets, and customer success indicators. The generated data is perfect for demos, training scenarios, dashboard development, and analytics testing.
Features

Realistic Data Patterns: Generates data that follows real-world customer implementation patterns
Multiple Implementation Stages: Creates accounts across different phases (Not Started, In Progress, Delayed, Complete)
Weighted Distributions: Uses realistic probability distributions for status, health scores, and other metrics
Time-Based Logic: Incorporates temporal relationships between planned dates, actual dates, and current metrics
Comprehensive Metrics: Includes health scores, feature adoption, support tickets, training completion, and more
Reproducible Results: Uses fixed random seed for consistent data generation
CSV Export: Outputs data in standard CSV format for easy import into various systems

Requirements

Python 3.6 or higher
No external dependencies (uses only Python standard library)

Installation

Clone or download this repository
Ensure Python 3.6+ is installed on your system
No additional packages need to be installed

Usage
Basic Usage
Run the script to generate demo data:
bashpython generate_sfdc_demo_data.py
This will create a file named sfdc_demo_data.csv with 30 fictional companies and their associated metrics.
Customization
You can easily customize the data generation by modifying the following variables in the script:
Company Names: Add or modify entries in the company_names list
pythoncompany_names = [
    "TechFlow Solutions", "GreenLeaf Consulting", 
    # Add your own company names here
]
Team Owners: Update the team_owners list with relevant names
pythonteam_owners = [
    "Sarah Chen", "Mike Rodriguez", 
    # Add your team member names here
]
Contract Values: Adjust the contract value ranges
pythoncontract_value = random.choice([25000, 35000, 50000, 75000, 100000, 150000, 200000])
Status Distributions: Modify the weights for implementation status distribution
pythonimpl_status = random.choices(
    implementation_statuses, 
    weights=[10, 30, 15, 45]  # Adjust these weights as needed
)
Generated Data Structure
The script generates a CSV file with the following columns:
ColumnDescriptionExample ValuesAccount_IDUnique account identifierACC-1000, ACC-1001Account_NameCompany nameTechFlow SolutionsTeam_OwnerAssigned customer success managerSarah ChenContract_ValueAnnual contract value50000, 100000Renewal_DateContract renewal date2025-12-15Implementation_StatusCurrent implementation phaseNot Started, In Progress, Delayed, CompleteGo_Live_Date_PlannedOriginally planned go-live date2025-08-15Go_Live_Date_ActualActual go-live date (if applicable)2025-08-22Implementation_Hours_LoggedTotal implementation hours85, 120Training_Sessions_AttendedSessions completed vs total3/4, 6/6Milestones_CompletedProject milestones achieved4/6, 8/8Days_Since_Go_LiveDays since actual go-live45, 120Health_ScoreCustomer health rating (1-10)8, 6, 9Last_Client_ContactDate of last interaction2025-07-20Feature_Adoption_RatePercentage of features being used75, 92Tickets_Last_30_DaysSupport tickets in last 30 days2, 8Most_Common_Ticket_TypePrimary ticket categoryTraining, Technical, BugAvg_Resolution_DaysAverage ticket resolution time2.5, 4.1Repeat_IssuesWhether issues are recurringY, NPayment_StatusCurrent payment standingCurrent, Late, OutstandingAccount_NotesContextual notes about the accountVarious status-appropriate notes
Data Logic and Patterns
The generator incorporates realistic business logic:
Implementation Status Distribution

Complete (45%): Most accounts should be successfully implemented
In Progress (30%): Active implementations in various stages
Delayed (15%): Troubled implementations requiring intervention
Not Started (10%): Pre-implementation accounts

Status-Specific Data Patterns
Not Started Accounts:

Minimal implementation hours logged
No feature adoption metrics
Future planned go-live dates
Basic contact patterns

In Progress Accounts:

Moderate implementation hours
Partial milestone completion
Some support tickets (mostly training/integration)
Regular contact patterns

Delayed Accounts:

High implementation hours (indicating struggles)
Poor training attendance
More support tickets with longer resolution times
Lower health scores

Complete Accounts:

All milestones completed
Feature adoption metrics populated
Support patterns based on time since go-live
Health scores reflecting customer satisfaction

Use Cases

Dashboard Development: Populate customer success dashboards with realistic data
Analytics Testing: Test reporting and analytics tools with varied data patterns
Training Scenarios: Provide realistic data for customer success training
Demo Environments: Create compelling demos with believable customer data
Process Development: Test workflows and automation with representative data
Performance Testing: Load systems with realistic data volumes and patterns

Extending the Generator
The script is designed to be easily extensible:

Add New Fields: Include additional columns by modifying the row dictionary and fieldnames list
Custom Business Logic: Implement industry-specific patterns or metrics
Integration Data: Add fields specific to your integration requirements
Scaling: Modify the company list or add generation loops for larger datasets
Different Industries: Customize company names, values, and patterns for specific verticals

Output
Running the script will generate:

sfdc_demo_data.csv: Complete dataset ready for import
Console output showing generation progress and sample data preview
Statistics showing the distribution of accounts across different implementation statuses

License
This project is licensed under the MIT License.
MIT License
MIT License

Copyright (c) 2025 Idea Junkies LTD

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
Contributing
Contributions are welcome! Areas for enhancement include:

Additional realistic data patterns
Industry-specific templates
More sophisticated temporal relationships
Integration with actual Salesforce APIs
Enhanced data validation and quality checks

Support
For questions, suggestions, or issues, please create an issue in the project repository or contact Idea Junkies LTD.
