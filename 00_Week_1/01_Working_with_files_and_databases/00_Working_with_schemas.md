# Working with Schemas in Talend Studio

Welcome to this presentation on working with schemas within Talend Studio. In this video, you'll explore what a schema is in the context of Talend Studio, see various types of schemas, and learn how to generate them.

## What is a Schema?

Schemas are used to define the structure of the data flowing within a job. They're attached to components, allowing these components to parse the input or output data before processing them. 

## Types of Schemas

Schemas of different types can be created for flat files, databases, or other data sources such as Talend MDM. If two components, such as a database and file-delimited component, work with data and have a similar data structure, then a schema of type generic can be created and used to configure both components.

### Examples of Schemas

1. **Flat File Schema Example 1**:
    - Each heading in the top row of the CSV file is added as an item of an appropriate type in the schema.
    - This schema could be used by a `tFileInputRaw` component to process the data.

2. **Flat File Schema Example 2**:
    - A product list created as an example file.
    - The schema definition uses each XML tag as a new item.
    - This schema can be used by an appropriate component, such as `tFileInputXML`.

### CSV File Example

When data is processed by a data flow component, a corresponding schema must be specified. 

- A CSV file processed by a `tFileInputDelimited` component, named `CustomersFile`.
- The schema for `CustomersFile` matches the data structure within the CSV file.
- The data flows to a `TDBOutput` component that uses a schema corresponding to the columns of the destination database table called `CustomersTable`.

## Generating Schemas in Talend Studio

Talend Studio allows you to generate the required schema in multiple ways.

### Using the Metadata Creation Wizard

- Right-click on a component in the repository and select the **Create** option to open the Metadata Creation Wizard window.
- Provide a metadata file name, select the file type, navigate to the file itself, define job settings like the field separator, whether to use the heading row to specify the column names, and define the schemas.

### Using Existing Metadata

- Use an existing DB connection to retrieve the schema of a database table by right-clicking the file and selecting **Retrieve Schema**.
- This opens the schema window and allows you to define the schema.

### Exporting and Importing Schemas

- To export, click the ellipses to the right of **Edit Schema** to open the Schema Edit window.
- Make sure **View Schema** is selected, then click the **Export All Rows into XML File** button. Name and save the file.
- To import, add a `tFileInputDelimited` component, click the ellipses to the right of **Edit Schema**, and click the **Replace All Rows by Import from XML File** button. Navigate to the file to import, click **Open** and **OK**.

### Copying and Pasting Schema Columns

- With a `tFileInputDelimited` component selected, click the ellipses to the right of **Edit Schema**, highlight the columns you want to copy, then click the **Copy Selected Items** button and click **OK**.
- Add another `tFileInputDelimited` component, click the ellipses, and click the **Paste** button to paste the columns.

### Synchronizing Columns

- Connect `CustomersFile` to `CustomersTable` with a main row, then select `CustomersTable`.
- In the component window, click the **Sync Columns** button. When you click the ellipses to the left, you can see the schemas are synced.

### Manually Adding Columns

- Add another `tFileInputDelimited` component, click the ellipses to edit the schema, and click the plus button to manually add a column. After defining it, click the plus again to add another column. You can add as many as you need.

## Conclusion

In this presentation, we discussed what a schema is in the context of Talend Studio, saw various types of schemas, and went over multiple ways to generate them. For more information about Talend Studio, please check out the other presentations in this series. 

Thanks for watching.
