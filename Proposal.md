# BDV3 Lab Project
Team members
- Fuchsberger Franz Xaver s2510454011
- Schachermair Florian s2510454025

## Dataset
[Backblaze Hard Drive Reliability Test Data](
https://www.backblaze.com/cloud-storage/resources/hard-drive-test-data#downloadingTheRawTestData)

The specific dataset we plan on using is the latest quarterly release: 2026 Data, Q2.

The dataset consists of one CSV file for every day of the quarter.
One row corresponds to a snapshot of one hard drive taken on that particular day.


### Size
The dataset is downloadable as a ZIP file with a size of
2.1 GB, which expands to 11.7 GB on disk, spread across 91 CSV files.

According to the [site](https://www.backblaze.com/cloud-storage/resources/hard-drive-test-data#snapshot)
it contains 354,415 drives, and over the time period, there are records of 31,553,350 drive days.

Since each drive day represents one row, the latter number also represents the number of rows.

### Columns

There are several columns to classify the drives, such as serial_number, the manufacturer model, and the capacity in bytes.

The "failure" column tracks hard drive failures, a 0 indicates the hard drive hasn't failed. A
1 means the drive failed and at that point it is removed and will not show up in future records.

The data comes from the data centers operated by Backblaze, so there are also several columns containing information about where the drives are installed, though these are not really relevant to this project.

Lastly, there are various columns recording [S.M.A.R.T.](https://en.wikipedia.org/wiki/Self-Monitoring,_Analysis_and_Reporting_Technology) attributes, which represent various operational properties of the drive.
For example:
- smart_9 Power-On Hours
- smart_12 Power Cycle Count
- smart_194 Temperature

The chosen examples are fairly self-explanatory, but there are also more complex attributes.
Different manufacturers may also have different ways of recording a specific value; for example, the "Read Error Rate" (smart_1) is a vendor-specific value.

### Research questions

Which vendor has the highest or lowest failure rate?

Does drive size correlate with failure rate?

What is the median age for drive failure?

(ML) Can we predict drive failure based on SMART attributes? (Needs refinement.)