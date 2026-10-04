# 📊 Montgomery-County-Crime-Database

A normalized relational database built in **MySQL 8.0** to organize, manage, and analyze more than **300,000 public crime records** reported by the Montgomery County Police Department (MCPD) from **July 2016 through January 2023**.

This project was completed as part of **INST327: Database Design and Modeling** at the University of Maryland, College Park.

## Project Overview

The project focused on transforming a large, unstructured crime dataset into a structured relational database capable of supporting reliable analysis of crime patterns across Montgomery County, Maryland.

The database was designed around questions such as:

- Which areas of Montgomery County experience the highest number of reported crimes?
- Which police districts and agencies respond to specific incidents?
- Which crime categories occur most frequently?
- How do crime patterns vary by location, time, district, and ZIP code?
- How can a large public-safety dataset be structured to support efficient SQL analysis?

The project involved data cleaning, normalization, relational schema design, SQL implementation, query development, and consideration of data ethics and privacy.

## Technologies

- **MySQL 8.0**
- **SQL**
- **Excel**
- Relational Database Design
- Entity-Relationship Modeling (ERD)
- Data Cleaning & Transformation
- Database Normalization

## Database Design

The final database consists of seven core tables:

| Table | Purpose |
|---|---|
| `Incident` | Stores individual reported crime incidents |
| `Offense` | Stores offense and crime classification information |
| `IncidentOffense` | Junction table connecting incidents to multiple offenses |
| `Location` | Stores incident location and geographic information |
| `District` | Stores policing district, sector, beat, and PRA information |
| `Agency` | Stores agency information associated with incidents |
| `Place` | Stores the type of location where an incident occurred |

The schema uses relational design principles to separate entities and reduce redundant data.

### Key Database Features

- **1NF–3NF normalization**
- Primary keys
- Foreign keys
- Composite primary keys
- Foreign key constraints
- Unique constraints
- Database indexes
- `AUTO_INCREMENT` surrogate keys
- Many-to-many relationships
- InnoDB storage engine
- `VARCHAR`, `INTEGER`, `DECIMAL`, and `DATETIME` data types
- Referential integrity

The `IncidentOffense` junction table was used to represent the many-to-many relationship between incidents and offenses, allowing a single incident to be associated with multiple offenses without repeatedly storing offense information.

## Data Preparation

The original MCPD dataset contained inconsistencies in formatting, missing values, duplicate information, and variations in offense descriptions.

The preprocessing process included:

1. Reviewing the raw dataset for structural and formatting issues.
2. Standardizing fields such as addresses, city names, and text formatting.
3. Identifying duplicate and inconsistent records.
4. Structuring attributes according to relational database principles.
5. Designing the normalized schema.
6. Validating the structure using a smaller test subset before scaling the design.
7. Loading the structured data into MySQL.

Excel was used during the extraction, transformation, and validation stages to help prepare the data for database implementation.

## SQL Analysis

The database supports SQL queries for analyzing crime patterns across Montgomery County.

Example analytical questions include:

- What is the total PRA in Montgomery County, and what is the average PRA for each city?
- Which crime category has the most total victims and incidents?
- Which areas experience the highest frequency of reported incidents?
- How do crime patterns vary by district, location, offense, and time?

These queries demonstrate how a normalized relational structure can be used to extract meaningful information from a large public-safety dataset.

## Entity Relationship Diagram

The project included an Entity Relationship Diagram (ERD) representing the relationships between the database entities.

**ERD:**  
<img width="694" height="507" alt="Screenshot 2026-10-04 at 2 57 58 PM" src="https://github.com/user-attachments/assets/b9e6a2b4-64ae-4cc3-8144-95c83e791f61" />


```text
![Montgomery County Crime Database ERD](images/erd.png)
```

## Project Architecture

```text
MCPD Public Crime Data
        │
        ▼
Data Cleaning & Standardization
        │
        ▼
Relational Schema Design
        │
        ▼
Normalization (1NF → 3NF) (Excel)
        │
        ▼
MySQL 8.0 Database (SQl)
        │
        ├── Incident
        ├── Offense
        ├── IncidentOffense
        ├── Location
        ├── District
        ├── Agency
        └── Place
        │
        ▼
SQL Queries & Analysis!
```

## Data Ethics & Privacy

Because the database contains geographically detailed public-safety information, responsible use and interpretation were an important part of the project.

Potential concerns include:

- Privacy risks associated with highly specific locations
- Misinterpretation of crime patterns
- Stigmatization of neighborhoods or businesses
- Potential misuse of police response-area information
- Bias resulting from combining crime records with unrelated demographic assumptions

The project deliberately avoided adding personally identifiable information and considered how analytical questions could unintentionally introduce bias or misrepresent communities.

## Team

This was a five-member team project completed for INST327 at the University of Maryland.

**Team Members:**
- Emilio Sanchez San Martin (me)
- Hein Htet
- Matthew Daniel
- Andy Gunawan
- Simran Shergill

## What I Learned

This project strengthened my experience with:

- Relational database design
- SQL and MySQL
- Database normalization
- Entity-relationship modeling
- Primary and foreign key design
- Many-to-many relationships
- Data cleaning and transformation
- Query-based data analysis
- Working with large real-world datasets
- Data integrity and validation
- Ethical considerations in public-safety data

One of the biggest lessons was learning how to break a large data problem into smaller, testable stages rather than attempting to clean and restructure the entire dataset at once.

## Future Improvements

Potential future development identified by the team includes:

- Integrating Census and other contextual datasets
- Adding GIS and spatial analysis capabilities
- Building automated ETL pipelines
- Improving data validation and anomaly detection
- Supporting predictive analytics and machine learning
- Implementing stronger access controls and privacy safeguards
- Developing a web-based application for interacting with the database

## Disclaimer

This repository represents an **academic database project** completed using publicly available MCPD crime data. It is intended for educational and analytical purposes and should not be interpreted as an official Montgomery County Police Department database or reporting system.
