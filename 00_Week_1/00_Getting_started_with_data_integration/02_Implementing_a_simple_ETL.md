# Creating a Simple ETL in Talend Studio

## Overview
- **Objective**:
  - Review the process of creating and running a standard data integration Job.
  - Example: Sorting a list of names from a file and outputting results to the console.

## Creating the Job
- Open the Integration perspective in Talend Studio.
- Right-click Job Designs in the Repository and select Create Standard Job.
- Name the Job "SimpleETL" and provide purpose and description.
- Add a tFileInputDelimited component to read from the sample data file.
  - Configure the component to point to the input file and set field separator and header options.
  - Define component schema to map fields in the file to output columns.

## Adding Components and Connecting Flows
- Add a tSortRow component to sort the data.
- Add a tLogRow component to display the sorted data.
- Connect components to allow data flow using right-click or drag-and-drop methods.

## Configuring Sorting
- Double-click the tSortRow component to configure sorting criteria.
- Set sorting criteria to sort names alphabetically.

## Running the Job
- Open the Run view and click the Run button to execute the Job.
- Monitor connections in the Designer and view output in the console.
- Review key concepts: input, output, and processing components; component configurations; schemas; flow connections; subJobs.

## Conclusion
- Talend Studio simplifies the creation of data integration Jobs.
- Understanding concepts like components, schemas, and flow connections is essential.
- Explore other presentations in this series for more information on Talend Studio and Data Integration.

