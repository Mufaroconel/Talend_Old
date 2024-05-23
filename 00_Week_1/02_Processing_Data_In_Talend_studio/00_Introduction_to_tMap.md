# Introduction to tMap

Welcome to this introduction to tMap.

## Overview of tMap Component

Talend provides a wealth of components that can perform a variety of data operations, but perhaps one of the most versatile and widely used is the tMap component, which we will look at more closely here.

Most processing components accept an input, perform some fixed transformation or calculation on the data, then emit the processed data through a single output. tMap is a flexible component that routes data from one main input and additional lookups to one or more outputs.

## Key Features of tMap

The ability to have an arbitrary number of inputs and outputs alone distinguishes tMap from most other components. In addition to routing data between the inputs and outputs, tMap can also process data as it is being routed. It supports a variety of predefined operations that you can customize using Java expressions. Processing can even be applied conditionally if needed.

With all these basic yet powerful capabilities, it would be difficult to find a problem that cannot be solved with a tMap component. With that in mind, let’s look at a common use case.

## Common Use Case: Remapping Data

It probably comes as no surprise that one of the biggest applications of the tMap component is to remap data. This is a common basic requirement when the schema you have doesn’t match up with what you need; you need to drop, add, combine, or transform columns to get the desired result.

Consider this example scenario: you have a database of customer information from which you would like to generate a mailing list. Comparing the input and output, notice that Customer ID is dropped, the name fields need to be combined, and the data needs to be enriched with two additional fields.

## Implementing the Use Case with tMap

### Step 1: Create and Configure the tMap Component

Here is an incomplete Job using a tMap component that has not been configured yet and is also not connected to an output. As no outputs for the tMap component have been defined yet, we'll create one by dragging the output side of tMap to the `tLogRow` component. Notice that Studio now prompts for a name because there can be any number of outputs. For this example, let's call this output “main”.

### Step 2: Open the tMap Editor

With the connection complete, we open the tMap editor by double-clicking the tMap component. This highlights another difference with tMap. While most components are configured in the Component view, tMap displays a separate window. This provides the screen real estate needed by the comprehensive GUI that enables you to configure all the options tMap has to offer.

### Step 3: Configure the Mapping

In the tMap editor, simply drag the desired columns from the input over to the output. We're omitting Customer ID because that is not needed in a mailing list, and we will also skip LastName for the moment. Notice how the relationship between the input columns and output columns is illustrated with the arrows.

Now we need additional columns for City and State. We add these in the schema editor below and leave these values as blank for now.

### Step 4: Combine Name Fields

The mailing list calls for a combined name field. Notice how the left column of the main output is labelled “Expression,” because that’s exactly what these values are – Java expressions. So, to combine the name fields into one, we'll open the expression builder and extend this into an expression that appends the last name with a space in between.

### Step 5: Finalize and Run the Job

The mapping is complete, so I will close the tMap editor and run the Job. Referring to the output, we see our data is now remapped and transformed as desired.

## Conclusion

In this presentation, we've seen that tMap can be a very powerful tool, and we've only touched on a few of the possibilities it has to offer. More complex lookups and output filtering, along with conditional and arbitrarily complex expressions, can dramatically increase the options that tMap provides.

To learn more about the tMap component, please refer to its documentation, and please check out the other presentations in this learning plan. Thanks for watching!
