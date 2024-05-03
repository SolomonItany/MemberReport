# Member Report Eligibility 

## Introduction
This is a Spark project that generates reports that deliver data about providers. Two reports are generated in a directory  named output in Json Formart.
The project also incorporates unit tests and packaging into a Docker image. Here's how to use it effectively:

**Prerequisites:**
- Docker: Ensure Docker is installed and running on your machine.
- SBT: Ensure SBT is installed for local development and testing.

## Instructions

**Step 1**: Update Data Files: Replace CSV Files: The project uses two CSV files for input data: member_eligibility.csv: Contains fields ID, fullName, and EligibilityDate and  member_months.csv: Contains fields memberID, Month, and Year. 
- Location: These files are located in the data directory.
- Editing: Modify these files as needed to update the input data.


**Step 2:** Build the Docker Image: Navigate to the project directory: cd /path/to/project Build the Docker image: `docker build -t member-report-generator .`

**Step 3:** Running the Docker Image: Run with Volume Mounts:To ensure the output is written to your local machine: `docker run -v ${PWD}/output:/app/output member-report-generator`

This mounts the local output directory to /app/output inside the container, where the reports are written. 

**Step 4:** Understanding the Test Cases: Unit Tests: 
- The project includes unit tests to validate functionality.

Test Cases: 
- Total Member Months: 
  - Ensures the report generates the correct total months per member.
- Member Months Per Month:
  - Validates the report's monthly totals per member. Run Tests Locally: sbt test
The test cases ensure the project functions correctly.

**Conclusion:**  This project generates reports, incorporating unit tests and packaging into Docker for portability. update data files  as you may like, and follow steps for docker image building, running the docker image, and testing the code functionality.
