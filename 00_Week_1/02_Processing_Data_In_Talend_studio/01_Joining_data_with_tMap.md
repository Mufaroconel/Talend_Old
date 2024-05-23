# Introduction to tMap: Joining Data

Welcome to this Introduction to tMap, where we talk about Joining Data.

## Overview

It’s often necessary to cross-reference data from one input against data from another. For example, in some cases, you might need to fetch additional information about a customer or product stored in a separate data source. In this case, we need to determine a city and state from a ZIP code to complete the addresses for a mailing list.

Here we have a Job that performs a simple remapping of input data to generate a mailing list, but the city and state are missing from the output. We added a new component to connect the Job to a ZIP code data source. We'll connect this new component as a new input to the tMap and reopen the tMap editor.

## Cross-Referencing Data

Notice that there are now two tables in the input column. Simply drag the ZIP column from the first input to the ZIP code column of the second input to create a cross-reference, known as a Join. Then, drag the City and State columns from the second input over to the corresponding columns in the main output. It’s that easy.

Running the Job with these changes, notice that most of the City and State fields are now populated with data pulled from the ZIP code database. These are the cities and states that map to the corresponding ZIP code for each record.

## Handling Missing Data

Notice that some fields are still null; some ZIP codes could not be found in the ZIP code database. For such cases, it would be preferable to exclude incomplete records from the mailing list and flag these records for review, as they are currently not addressable. For this case, we’d like to establish a second output that captures records containing ZIP codes that could not be found.

To do this, we’ll need to take a close look at the join model used in the tMap component. By default, tables apply a Left Outer join, which behaves as we’ve seen; lookups that fail assume null values in the output.

## Changing the Join Model

We'll change this to an Inner join. Using this model, lookups that fail will be omitted from the main output, but we have the option of catching the rejects into a separate output, which I am defining now. For this new output, we set the "Catch lookup inner join reject" option to true.

The next decision we have to make is which columns we would like to see there. Usually, this would be a decision best left to the data stewards within your organization, but for now, we will propagate the name, address, and ZIP code.

## Finalizing the Configuration

The final step involves connecting this newly defined output to a newly defined `tLogRow` component that displays the entries with a bad ZIP code. We want to link the output we’ve already defined. To do this, we right-click the tMap component, then select and link the output as shown here.

Running the updated Job, notice how the main mailing list now contains only addressable records, and the failed lookups are gathered into the separate output.

## Conclusion

In this presentation, we've seen that tMap can be a very powerful tool, and we've only touched on a few of the possibilities it has to offer. More complex lookups and output filtering, along with conditional and arbitrarily complex expressions, can dramatically increase the options that tMap provides.

To learn more about the tMap component, please refer to its documentation, and please check out the other presentations in this learning plan. Thanks for watching!
