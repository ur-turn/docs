---
title: UR TURN Docs 

language_tabs: # must be one of https://git.io/vQNgJ
  - csv 

includes:
  - powerschool 

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

## attendance.csv

The IMS One Roster Specification does not provide student attendance records. As
a result, we'll need an extract with the columns below.

<aside class="notice">
Frequency: Daily.
</aside>

<aside class="notice">
Range: Records from 8th grade to current for enrolled students.
</aside>

|Column Field Header|Required|Format |Description|
|-------------------|--------|-------|-----------|
|schoolId           |Yes     |       |The school ID in [orgs.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293263)
|studentId          |Yes     |       |The student ID in [users.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293266)|
|courseId           |Yes     |       |The course ID in [courses.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293259).
|endYear            |Yes     |Integer|For a school year 2018-2019, endYear is 2019.
|date               |Yes     |Date   |The date of the absence.|
|period             |No      |Integer|[RFC]
|code               |Yes     |String |[RFC] The district/school code identifying the type of absence.|
|status             |Yes     |String |[RFC]

## transcripts.csv 

Predicting a student's future sucess is largely based on their previous academic accomplishments.

<aside class="notice">
Frequency: At a minimum, we request files be updated at the end of each term. It
may be easier to have the extracts generated nightly along with the attendance.
</aside>

<aside class="notice">
Range: Records from 8th grade to current for enrolled students.
</aside>

|Column Field Header|Required|Format |Description|
|-------------------|--------|-------|-----------|
|schoolId           |Yes     |       |The school ID in [orgs.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293263)
|studentId          |Yes     |       |The student ID in [users.csv](https://www.imsglobal.org/oneroster-v11-final-csv-tables#_Toc480293266)|
|grade              |Yes     |Integer|The student's grade level at the time of the credit.
|schoolYear         |Yes     |Integer|The academic school year at the time of the credit. For 2018-2019, this would be 2019.
|courseNumber       |Yes     |       |[RFC]
|courseName         |Yes     |String |Name of the course.
|score              |Yes     |String |The grade recieved: e.g. A, B, C, D, or F. + and - also accepted.
|creditType         |Yes     |String |The course subject the credit is attributed to. e.g. English, Math 
|creditEarned       |Yes     |Float  |The value of the credits earned by the score.
|gpaWeight          |        |Float  |[RFC]
|gpaValue           |        |Float  |[RFC]
|unweightedGpaValue |        |Float  |[RFC]
|bonusPoints        |        |Float  |[RFC]
|honorsCode         |        |Float  |[RFC]
|startTerm          |        |       |[RFC]
|endTerm            |        |       |[RFC]
|termsLong          |        |       |[RFC]
|actualTerm         |        |       |[RFC]



```csv
studentId,schoolId,grade,schoolYear,courseNumber,courseName,score,creditType,creditEarned,gpaWeight,gpaValue,unnweightedGpaValue,bonusPoints,honorsCode,startTerm,endTerm,termsLong,actualTerm
```

