# Real-Time Data Ingestion with Delta Lake

This project showcases a simple yet effective pipeline for ingesting and storing real-time data using PySpark and Delta Lake. It generates mock user information and writes it to a Delta table at regular intervals, while maintaining version control and delivering email updates after each cycle.

## Objective

To develop a pipeline that:
- Creates synthetic user data (Name, Address, Email)
- Continuously adds this data to a Delta Lake table without replacing previous entries
- Tracks all table updates using built-in version history
- Sends email alerts after each scheduled data ingestion, summarizing recent changes

## Key Highlights

- Configurable ingestion interval (default: every 5 minutes)
- Delta Lake for atomic and scalable data storage with version history
- Time zone support for consistent timestamping
- Automatic email notifications with formatted HTML summaries
- Uses Faker for creating realistic test data

## Technologies Used

| Tool/Library       | Purpose                                     |
|--------------------|---------------------------------------------|
| PySpark            | Distributed data processing framework       |
| Delta Lake         | Transactional storage with version control  |
| Faker              | Generates sample user data for testing      |
| schedule (Python)  | Sets the time interval for data ingestion   |
| smtplib, email     | Used to send email reports after each run   |
| IPython.display    | Renders HTML summaries in Jupyter/Colab     |

Due to authentication restrictions in environments like Google Colab, integrating email functionality directly within the notebook posed challenges.
As a workaround, a separate Python script (email_summary.py) was developed to send the summary email in HTML format successfully.
This separation allows the main ingestion pipeline to execute smoothly without being blocked by email-related errors, while also enabling independent testing of the notification component.


