# BDV3 Lab Project
Team members
- Fuchsberger Franz Xaver s2510454011
- Schachermair Florian s2510454025

## Dataset
[Backblace Hard Drive Reliability Test Data](
https://www.backblaze.com/cloud-storage/resources/hard-drive-test-data#downloadingTheRawTestData)

The specific dataset we plan on using is latest quarterly release: 2026 Data, Q2.

The dataset consists of 1 csv for every day of the quarter.
One row corresponds to a snapshot of 1 hard drive on taken on that particular day.


### Size
The dataset is downloadable as a Zip File with 
2.1 GB, which expand to 11.7 GB on Disk spread across 91 .csv files.

According to the [site](https://www.backblaze.com/cloud-storage/resources/hard-drive-test-data#snapshot)
it contains 354,415 drives, and over the time period therre are records of 31,553,350 drive days.

Since each drive day represents one row that means latter number also represents the number of rows.

### Columns

There several columns to classify the drives such as serial_number, the (manufacturer) model,and the capacity in bytes.

The "failure" column tracks hard drive failures, a 0 indicates the hard drive hasn't failed. A
1 means the drive failed and at that point it is removed and will not show up in future records.

The data comes from the datacenters operated by Backblaze, so there also several columns containing information where the drives are installed, though these are not really relevant for this project.

Lastly there are various columns recording [S.M.A.R.T](https://en.wikipedia.org/wiki/Self-Monitoring,_Analysis_and_Reporting_Technology) attributes which represent various oprational properties of the drive.
For example:
- smart_9 Power-On Hours
- smart_12 Power Cycle Count
- smart_194 Temperature

The chosen examples are fairly self explanatory, but there are also more complex attributes.
Also different manufacturers may have a different way of recording a specific value, for example the "Read Error Rate" (smart_1) is a vendor specific value.

### Research questions

Which vendor has the highest/lowest failure rate?

Does drive size correlate with failure rate?

What is the median age for drive failure?

(ML) Can we predict drive failure based on smart attributes? (needs refinement)