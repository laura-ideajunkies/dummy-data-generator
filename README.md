# SFDC Demo Data Generator

A Python script that generates realistic Salesforce (SFDC) customer success and implementation data for demonstration, testing, and training purposes.

## Overview

This tool creates synthetic customer account data that mirrors real-world Salesforce implementations, including various implementation stages, health metrics, support tickets, and customer success indicators. The generated data is perfect for demos, training scenarios, dashboard development, and analytics testing.

## Features

- **Realistic Data Patterns**: Generates data that follows real-world customer implementation patterns
- **Multiple Implementation Stages**: Creates accounts across different phases (Not Started, In Progress, Delayed, Complete)
- **Weighted Distributions**: Uses realistic probability distributions for status, health scores, and other metrics
- **Time-Based Logic**: Incorporates temporal relationships between planned dates, actual dates, and current metrics
- **Comprehensive Metrics**: Includes health scores, feature adoption, support tickets, training completion, and more
- **Reproducible Results**: Uses fixed random seed for consistent data generation
- **CSV Export**: Outputs data in standard CSV format for easy import into various systems

## Requirements

- Python 3.6 or higher
- No external dependencies (uses only Python standard library)

## Installation

1. Clone or download this repository
2. Ensure Python 3.6+ is installed on your system
3. No additional packages need to be installed

## Usage

### Basic Usage

Run the script to generate demo data:

```bash
python generate_sfdc_demo_data.py
```

This will create a file named `sfdc_demo_data.csv` with 30 fictional companies and their associated metrics.

### Customization

You can easily customize the data generation by modifying the following variables in the script:

**Company Names**: Add or modify entries in the `company_names` list
```python
company_names = [
    "TechFlow Solutions", "GreenLeaf Consulting", 
    # Add your own company names here
]
```

**Team Owners**: Update the `team_owners` list with relevant names
```python
team_owners = [
    "Sarah Chen", "Mike Rodriguez", 
    # Add your team member names here
]
```

**Contract Values**: Adjust the contract value ranges
```python
contract_value = random.choice([25000, 35000, 50000, 75000, 100000, 150000, 200000])
```

**Status Distributions**: Modify the weights for implementation status distribution
```python
impl_status = random.choices(
    implementation_statuses, 
    weights=[10, 30, 15, 45]  # Adjust these weights as needed
)
```

## Generated Data Structure

The script generates a CSV file with the following columns:

| Column | Description | Example Values |
|--------|-------------|----------------|
| `Account_ID` | Unique account identifier | ACC-1000, ACC-1001 |
| `Account_Name` | Company name | TechFlow Solutions |
| `Team_Owner` | Assigned customer success manager | Sarah Chen |
| `Contract_Value` | Annual contract value | 50000, 100000 |
| `Renewal_Date` | Contract renewal date | 2025-12-15 |
| `Implementation_Status` | Current implementation phase | Not Started, In Progress, Delayed, Complete |
| `Go_Live_Date_Planned` | Originally planned go-live date | 2025-08-15 |
| `Go_Live_Date_Actual` | Actual go-live date (if applicable) | 2025-08-22 |
| `Implementation_Hours_Logged` | Total implementation hours | 85, 120 |
| `Training_Sessions_Attended` | Sessions completed vs total | 3/4, 6/6 |
| `Milestones_Completed` | Project milestones achieved | 4/6, 8/8 |
| `Days_Since_Go_Live` | Days since actual go-live | 45, 120 |
| `Health_Score` | Customer health rating (1-10) | 8, 6, 9 |
| `Last_Client_Contact` | Date of last interaction | 2025-07-20 |
| `Feature_Adoption_Rate` | Percentage of features being used | 75, 92 |
| `Tickets_Last_30_Days` | Support tickets in last 30 days | 2, 8 |
| `Most_Common_Ticket_Type` | Primary ticket category | Training, Technical, Bug |
| `Avg_Resolution_Days` | Average ticket resolution time | 2.5, 4.1 |
| `Repeat_Issues` | Whether issues are recurring | Y, N |
| `Payment_Status` | Current payment standing | Current, Late, Outstanding |
| `Account_Notes` | Contextual notes about the account | Various status-appropriate notes |

## Data Logic and Patterns

The generator incorporates realistic business logic:

### Implementation Status Distribution
- **Complete (45%)**: Most accounts should be successfully implemented
- **In Progress (30%)**: Active implementations in various stages
- **Delayed (15%)**: Troubled implementations requiring intervention
- **Not Started (10%)**: Pre-implementation accounts

### Status-Specific Data Patterns

**Not Started Accounts**:
- Minimal implementation hours logged
- No feature adoption metrics
- Future planned go-live dates
- Basic contact patterns

**In Progress Accounts**:
- Moderate implementation hours
- Partial milestone completion
- Some support tickets (mostly training/integration)
- Regular contact patterns

**Delayed Accounts**:
- High implementation hours (indicating struggles)
- Poor training attendance
- More support tickets with longer resolution times
- Lower health scores

**Complete Accounts**:
- All milestones completed
- Feature adoption metrics populated
- Support patterns based on time since go-live
- Health scores reflecting customer satisfaction

## Use Cases

- **Dashboard Development**: Populate customer success dashboards with realistic data
- **Analytics Testing**: Test reporting and analytics tools with varied data patterns
- **Training Scenarios**: Provide realistic data for customer success training
- **Demo Environments**: Create compelling demos with believable customer data
- **Process Development**: Test workflows and automation with representative data
- **Performance Testing**: Load systems with realistic data volumes and patterns

## Extending the Generator

The script is designed to be easily extensible:

1. **Add New Fields**: Include additional columns by modifying the row dictionary and fieldnames list
2. **Custom Business Logic**: Implement industry-specific patterns or metrics
3. **Integration Data**: Add fields specific to your integration requirements
4. **Scaling**: Modify the company list or add generation loops for larger datasets
5. **Different Industries**: Customize company names, values, and patterns for specific verticals

## Output

Running the script will generate:
- `sfdc_demo_data.csv`: Complete dataset ready for import
- Console output showing generation progress and sample data preview
- Statistics showing the distribution of accounts across different implementation statuses

## License

This project is licensed under the MIT License.

### MIT License

```
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
```

## Contributing

Contributions are welcome! Areas for enhancement include:
- Additional realistic data patterns
- Industry-specific templates
- More sophisticated temporal relationships
- Integration with actual Salesforce APIs
- Enhanced data validation and quality checks

## Support

For questions, suggestions, or issues, please create an issue in the project repository or contact Idea Junkies LTD.