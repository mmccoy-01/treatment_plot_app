This is a `shiny` application that randomizes mice to treatment arms based on their bioluminescent flux values. The point of this is to reduce experimental bias by making sure that mice are at equivalent levels of disease burden before treatment assignment.

## How it works:
The user uploads a .csv file of bioluminescent mouse data computed from Living Image™. The user selects which mice will be non-study and defines the number of arms and the number of mice per arm. The randomization process searches for the seed that has the least amount of total_flux variability both between and within groups. The 'total_variability' metric is a combined metric that accounts for both between-group and within-group variability by using the sum of the standard deviations of the mean total flux between groups and the standard deviations within groups. This metric is on a user-selected scale which allows for preferential weighting to either the variability between groups or within groups.

## Format of .csv file input:
This is how your columns should be named:
cage_number,	id,	ear_punch,	imaging_date,	total_flux,	avg_radiance

* imaging_date is in ISO 8601 international standard which expresses a date as “2001-02-13” (yyyy-mm-dd)
