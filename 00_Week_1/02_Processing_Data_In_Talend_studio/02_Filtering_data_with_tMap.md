# Presentation on Filtering Data Using a tMap Component

Welcome to this presentation on filtering data using a tMap component. tMap has many flexible capabilities, making it suitable for a wide variety of use cases.

## Introduction to tMap Filtering

This demonstration shows you its built-in ability to filter data coming in or going out based on arbitrary conditions.

## Job Setup and Inputs

Here we have a Job that processes a list of customers and generates a mailing list. As an input, it uses a database table containing a list of customer names and zip codes and a zip code data source that furnishes complete information for each known zip code. In this case, we're interested in the city and state data.

## Job Outputs

The two outputs are:
- The main output of this job, which delivers a list of complete address records obtained by cross-referencing the ZIP codes from the input with the ZIP code data source in an operation known as an inner join.
- The secondary output, which catches join rejects, i.e., records containing incorrect zip codes.

All of this is achieved using the mapping and join capabilities of the tMap component. Now let's reconfigure this job to deal with a subset of the data, for example, to process customers in three separate batches.

## Configuring the Filter

The sensible way to do this is to filter customers based on the alphabetic placement of their last name. Let's configure the tMap component to only process the last names starting with the letters A through I.

1. Open the tMap editor by double-clicking the tMap component.
2. On the left side, the two input table names match the connection rows in the designer. Row 1 for the main input and Row 2 for the lookup input. For better clarity, you can rename the connection rows in the designer.
3. We want to activate expression filtering on the main input, Row 1, so we'll click the enable/disable expression filter button for that input, opening a text field to enter the filter expression.
4. Populate this field with a simple expression that evaluates to true if the first character of the last name column is in the range of A through I. Only records that pass this test will be processed.
5. Close the editor and run the updated job.

## Running the Job

Notice that the main input flow carries the entire collection of 10 records to the tMap. However, only five of those are passed on to the various outputs. The other five records were not processed because they didn't pass the filter we added. We can verify this by looking at the output in the console. Notice that all of the last names fall within the prescribed range.

## Different Use Case: Filtering by State

Now let's consider a different use case. Suppose we only want to generate a list of addresses for customers residing in a specific state, say Texas.

1. Go back to the tMap editor.
2. First, disable the filter we added previously. We don't have to delete our work entirely. Click the enable/disable expression filter button again to turn that filter off.
3. We want to filter based on a state, but the state is only known following a successful lookup. These are emitted through the main output of the tMap component. So let's enable a filter condition.
4. Referring to the output columns, we see that the Java expression populating the state column is coming from `row2.state`. That is the state column from the lookup table. So let's create an expression using that as a basis. In this example, we will hard-code the state code we're comparing against. However, in a general-purpose example, this value might be fed by an easily configurable element, such as a context variable.
5. Close the editor and run the updated job.

The main input flow carries 10 records to the tMap, four of which are rejected. We'd expect the remaining six on the main output, but there are only two, due to the new filter we introduced. Looking at the output, we can confirm our filter works because it only displays customer records from the state of Texas.

## Conclusion

This presentation only scratches the surface of what's possible when using tMap filtering on inputs and outputs. Refer to the tMap documentation for more examples to inspire your next project. And you can check out the other tMap presentations in this series. Thanks for watching!
