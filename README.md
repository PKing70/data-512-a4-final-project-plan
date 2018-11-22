# Assignment 4: Final project plan

Patrick King

Professor Morgan

DATA 512

20 November 2018

## How to get Chosen by Donors

[DonorsChoose](https:www.donorschoose.org) is a crowd-sourced nonprofit organization that provides a platform for teachers to request funding for classroom supplies and projects. Donors can then peruse the advertised projects on the site, to choose which causes to support based on information garnered from the page created for each plea by the teacher or class. These "attractor" pages are standardized, containing uniform components such as classroom data, category of project, essays or short-form paragraphs covering how the funds will be used, financial goals, a statuss bar tracking progress towards financial goal, and other components. DonorsChoose has made public many years of its project data, tracking these attributes and donation results over many years. My project will statistically analyze the DonorsChoose public datasets to identify factors that result in more (or less) effective project funding request pages. 

I want to do this project to learn how teachers could imrove the effectiveness of their crowdfunding efforts. I hope that trends and correlations can be shown that might help teachers attract more donations by creating their funding pages using the options and tactics that have roven to achieve funding completion or higher rates of donation. I could share this information to teaching communities or discussion groups for feedback, which might help others better use crowdfunding through DonorsChoose to meet their classroom expense needs. 

The DonorsChoose approach to funding education expenses is a valuable alternative for teachers who often must use personal funds to equip their classrooms or to enable novel learning experiences. Helping teachers understand the effectiveness or shortcomings of various options in setting up, describing, and categorizing their projects might increase the rates of donation, or perhaps it might produce a "zero-sum" result where some teachers become more capable at attracting donations, essentially at the expense of the other teachers using less effective project designs. Finally, my motivations are not purely altruistic as first, I intend to share my analysis with my underfunded high school-teaching wife who often funds her ideas and classrooms from our savings, typically without reimbersement from her school district. "Charity begins at home..." (Browne, 141).

## Research Questions and Analysis

I intend to explore the data to find correlations (or lack thereof) in areas such as:

1. Do specific project types garner more funding than others?
2. Do specific class locations garner more funding than others?
3. Do specific giving page traits (such as "Thank you notes sent") garner more funding than others?

I expect that these questions and related ones will support traditions linear regression modelling and plotting, where I hope to be able to identify variables that have shown to be particularly successful or unsuccessful at attracting donations to projects. For example, given that a giving page must use pre-defined categories for primary_focus_subject (e.g. "Environmental Science"), some subjects might be better-funded than others. Perhaps certain donor regions (such as the Seattle area or San Francisco area) might support particular subjects ("Computer Science"), while others regions (such as Iowa from which I write this project plan) might better support different subjects ("Agricultural Science").

### Deliverables

I expect to use Python in a Jupyter Notebook to load and explore the data from some combination of the below data soucr options, to be able to investigate my hypotheses, perhaps develop different hypotheses, and report meaningful correlations between project variables and outcomes such as primary_focus_subject="Art" results in goal reach and funding rates. The deliverable should be one .ipynb, its supporting data .csv files, and any .png files corresponding to generated visualizations, in a Github repository parallel to this one. 

## Data Sourcess

DonorsChoose has made thirteen years of its data open and publicly accessible for analysis. The data includes information that I have downloaded and begun analysis on:

* Projects (including classroom projects that have been posted, school information such as government-issued NCES ID, lat/long, and city/state/zip)
* Donations (including donation amounts, donor city, state)
* Project resources (including materials/resources requested for the classroom projects, including vendor name)
* Project essays (including the full text of the teacher-written requests accompanying all classroom projects)
* Giving pages (number of teachers, students, amount raised)

and more, such as gift card data which I do not intend to use.

### Option 1: Raw data

Guidelines are provided to access the full set of all their available data in CSV form at the DC [OpenData Layout and Docs page](https://research.donorschoose.org/t/opedata-layout-and-docs/18). 

According to the documentation, "the data is compressed, quoted, escaped and without a header. To properly import, use Python's pandas using code in 'How to read this CSV file' under each button. No need to decompress files." Each data file comes in a compressed .GZ archive, which I've extracted using WinZip for Windows.

To import the project data into Python pandas 235, for example, I should execute this command:

```python
projects = pandas.read_csv('opendata_projects000.gz', escapechar='\\', names=['_projectid', '_teacher_acctid', 
'_schoolid', 'school_ncesid', 'school_latitude', 'school_longitude', 'school_city', 'school_state', 'school_zip', 
'school_metro', 'school_district', 'school_county', 'school_charter', 'school_magnet', 'school_year_round', 
'school_nlns', 'school_kipp', 'school_charter_ready_promise', 'teacher_prefix', 'teacher_teach_for_america', 
'teacher_ny_teaching_fellow', 'primary_focus_subject', 'primary_focus_area' ,'secondary_focus_subject', 
'secondary_focus_area', 'resource_type', 'poverty_level', 'grade_level', 'vendor_shipping_charges', 'sales_tax', 
'payment_processing_charges', 'fulfillment_labor_materials', 'total_price_excluding_optional_support', 
'total_price_including_optional_support', 'students_reached', 'total_donations', 'num_donors', 
'eligible_double_your_impact_match', 'eligible_almost_home_match', 'funding_status', 'date_posted', 'date_completed', 'date_thank_you_packet_mailed', 'date_expiration'])
```

The DonorsChoose data site provides extensive documentation for the schemas of theses tables and guidelines for joining them as needed using PostGre SQL, according to this schema/ER diagram:

![schema](donorschoose.png)

I expect to join and filter Projects, Donations and Resources to investig

### Option 2: Pre-selected data

However, I might not tackle such SQL work to perform my analysis. Alternately, the datasets have already been decompressed, joined, and filtered into significant subsets to produce Looker visualizations. Therefore, depending upon the direction of my exploration, I might choose to download these more focused CSV files instead of the raw data discussed above.

### Option 3: API data

DonorsChoose also makes its data available through a REST API.

## License Information

This DonorsChoose data is licensed under a Creative Commons Attribution-NonCommercial 3.0 Unported License ([CC BY-NC 3.0](https://creativecommons.org/licenses/by-nc/3.0/us/)). It is available for non-commercial use, and they provide these guidelines for commercial use: "If you'd like to use this data for commercial purposes, get in touch with us and tell us a bit about your plans. Our strong preference is to greenlight your commercial application with no licensing fees, and we have never charged for access to our API or data. We just need to make sure that the application won't run contrary to our org's mission, abuse the rich content that our teachers have created, etc" (DonorsChoose Data, Download Opendata License section).

## Additional Human Centered Data Science Considerations

Crowdfunding education is positioned by DonorsChoose founder <name> as a solution. However, others consider it contrary to the democratization of decision making. (fast company). Others have concerns that DonorsChoose de-incentivizes school districts and administrations from adequately funding their schools.
  
Whether it is ultimately worthwh
  
## Works Cited

Althoff, Tim and Leskovec, Jure. "Donor Retention in Online Crowdfunding Communities: A Case Study of DonorsChoose.org." *ACM International Conference on World Wide Web (WWW)* 2015 [<https://cs.stanford.edu/people/jure/pubs/donors-www15.pdf>](https://cs.stanford.edu/people/jure/pubs/donors-www15.pdf).

Browne, Thomas. *Religio Medici : The Religion of a Doctor.* Sir Thomas Browne site: University of Chicago. Web. 21 November 2018 [<http://penelope.uchicago.edu/relmed/relmed1645.pdf>](http://penelope.uchicago.edu/relmed/relmed1645.pdf).

DonorsChoose Data. "Download Data". Web. 21 November 2018 [<https://research.donorschoose.org/t/download-opendata>](https://research.donorschoose.org/t/download-opendata)

Tyre, Peg. "Beyond School Supplies: How DonorsChoose is Crowdsourcing Real Education Reform." FastCompany 2 October 2014: n.
pag. Web. 21 November 2018 [<https://www.fastcompany.com/3025597/donorschoose-hot-for-teachers>](https://www.fastcompany.com/3025597/donorschoose-hot-for-teachers).



●Are there any unknowns or dependencies that might affect your ability to complete this project? 

●How do human-centered design considerations inform... a.your decision to pursue this projectb.your approach to performing the work?

What type of data and analysis?

Talking about genderMany projects are centred on gender as a variable. Since the assignment requires you to think about ethics, consider what ‘gender’ is:

●Not the same as sex (‘man’, ‘woman’ not ‘male’, ‘female’)

●Not a binary (people have identities other than ‘man’ or ‘woman’)

●Not impermeable (people transition between genders)

●Something that creates myriad different experiences of life that are likely to be reflected in your data.

Talking about genderQuestions to ask:

●Does your data only contain binary options? If so, note that as a limitation - and note why it is a limitation (it excludes people outside that binary).

●Does your data include trans people? If so, incorporate that into the gender research. If not, highlight that as a limitation


