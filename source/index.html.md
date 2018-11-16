---
title: UR TURN Docs 

language_tabs: # must be one of https://git.io/vQNgJ
  - csv 

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

search: true
---

# Introduction
 
 Welcome to UR TURN's technical documentation. You can use this as a reference to
 help you prepare your data extracts so students can begin to plan their path to
 success.

Right now, we only have example data extracts. We are open to posting code
examples for different SIS platforms. Feel free to reach out and we'll begin the
conversation.

# Security & Privacy

Every school has its own account to upload files to using SFTP. We will provide
credentials to the technical administrator using [onetimesecret.com](https://onetimesecret.com/)

# File Formats

Every file should be in the CSV (comma separated values) file format. 

Details are found in [RFC-4180](https://tools.ietf.org/html/rfc4180) and the [IMS OneRoster&reg; CSV Format Specification v1.1](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293252).
The OneRoster&reg; specification has the extra restriction that carriage-returns
are not permitted within a field.

<aside class="notice">
Fields containing commas and double-quotes must be enclosed in double-quotes. If double-quotes are used to enclose a field, then a double-quote appearing inside the field must be escaped by preceding it with another double-quote.

For the sake of your sanity, we also accept CSV files delimited with a pipe. e.g. |
</aside>

# Data Extracts

## Classes, Courses, Enrollments, Schools, Students, & Parents 

A good portion of the data UR TURN uses is provided by data files which already
may be available to you. They are the [IMS OneRoster&reg; CSV Tables Specification v1.1](https://www.imsglobal.org/oneroster-v11-final-csv-tables).  

UR TURN needs a subset of the OneRoster&reg; reports. They are:

* [classes.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293256)
* [courses.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293259)
* [enrollments.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293261)
* [orgs.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293263)
* [users.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293266)

<aside class="notice">
Frequency: Daily.
</aside>

## Attendance

The IMS One Roster Specification does not provide student attendance records. As
a result, we'll need an extract with: [list fields here].

```csv
studentId,schoolId,endYear,date,period,code,status,excuse,courseId
```

<aside class="notice">
Frequency: Daily.
</aside>

<aside class="notice">
Range: Records from 8th grade to current for enrolled students.
</aside>

## Academic Transcripts 

Predicting a student's future sucess is largely based on their previous academic accomplishments.

```csv
studentId,schoolId,grade,schoolYear,courseNumber,courseName,score,creditType,creditEarned,gpaWeight,gpaValue,unnweightedGpaValue,bonusPoints,honorsCode,startTerm,endTerm,termsLong,actualTerm
```

<aside class="notice">
Frequency: At a minimum, we request files be updated at the end of each term. It
may be easier to have the extracts generated nightly along with the attendance.
</aside>

<aside class="notice">
Range: Records from 8th grade to current for enrolled students.
</aside>
