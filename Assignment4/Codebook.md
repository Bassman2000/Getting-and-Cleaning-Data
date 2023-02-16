The unzipped data files and folder structure are included in the repository. Maintaining the structure (e.g. via cloning the repo) will allow the run_analysis.R script to run.

run_analysis.R:

1. Read training dataset files (X_train.txt, y_train.txt and subject_train.txt) and test dataset (X_test.txt, y_test.txt and subject_test.txt). Training and test data are combined to produce data frames *X*, *y* and *subject*, which form the basis of the remaining analysis.<br /><br />
2. Columns are given meaningful names. Feature names were manually taken from feature.txt.<br /><br /> 
3. Drop columns of *X* that do not represent a mean or a std measurement.<br /><br />
4. Create data frame *tot* which is just *X* with the subject ID (1...30) as column 1 and the numerical activity designation (1...6) as column 2.<br /><br />
5. A new column, activityname, is created in data frame *y*. activity name contains the string naming the activity associated with the numerical value (1..6) in column activity. *y* is left as a look-up table and the string value of the activity name is not included in *tot*.<br /><br />
6. A new data frame *tot_summary* is created by grouping by subject and activity and calculating the mean of all features remaining from 3. above.

The data frame tot_summary (i.e. the summary, tidy table) has 180 rows, consistent with summarizing by 30 subjects x 6 activities.
