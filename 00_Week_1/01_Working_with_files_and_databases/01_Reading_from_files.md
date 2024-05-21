# Working with Files in Talend Studio

Welcome to this presentation on working with files in Talend Studio. In this presentation, you'll learn how to import data files in a data integration Job in Talend Studio. We'll cover the necessary steps to import data from files.

A common application in data integration is to merge data coming from different files using the ETL process. This video addresses the problem of reading data from files with different formats, such as CSV, XML, and JSON. Regardless of the file type, data is interpreted and processed in the same way using the following three steps:

1. **Identify the File Properties**: This ensures that data can be properly extracted from the file and separated into fields.
2. **Define a Schema**: Map each field of the imported data to a column.
3. **Configure File Properties and Schema in a Dedicated Component**: Read data from the source file.

## File Properties and Schema

The properties of a file depend on its type. Take a look at the structure of your delimited or hierarchical file. This will help you define how to extract data into fields. The schema sets the properties of the output columns, such as name, types, lengths, and so on. You can build the schema manually, or import it from the Repository or from another file.

Pick a component in the palette and configure it using the file properties and the schema. The name of the component starts with ‘FileInput’, followed by the file type, for example, `tFileOutputDelimited`, `tFileOutputXML`, `tFileOutputJSON`.

And that’s it, you have your first component ready for the Load operation of the ETL process.

## Example: Delimited File

Let’s start with a delimited file. For this presentation, we'll use a typical list of customers. Most of the time, the first rows are dedicated to field headers. They contain the field labels but no customer data. In this example, we have six fields which you can see here.

Each data row needs to end with a row separator. If you don't see one, consider the standard newline character used here. Each row is divided into fields by a field separator, also called a delimiter. The field separator used here is a comma.

## Configuring the Component

Let’s reuse these properties to configure the component.

1. Place a `tFileInputDelimited` component in the Designer and display it in the Component view.
2. Fill in the main properties:
    - File path and name
    - Row separator
    - Field separator
    - Number of rows in the headers

From the Component view, you must edit or import the schema. Using the schema definition, fields are mapped to the columns. Data is ready to be consumed by the next component in the data flow.

## Conclusion

In this presentation, we covered all the steps of the processing pipeline to import data from files in a data integration Job in Talend Studio. We saw practical examples with delimited, XML, and JSON files.

