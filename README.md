# Assignment 4: Final project plan

Patrick King

Professor Morgan

DATA 512

20 November 2018

## How to get Chosen by Donors

[DonorsChoose](https:www.donorschoose.org) is a crowd-sourced nonprofit organization that provides a platform for teachers to request funding for classroom supplies and projects. Donors can then peruse the advertised projects on the site, to choose which causes to support based on information garnered from the page created for each plea by the teacher or class. These "attractor" pages are standardized, containing uniform components such as classroom data, category of project, essays or short-form paragraphs covering how the funds will be used, financial goals, a statuss bar tracking progress towards financial goal, and other components. DonorsChoose has made public many years of its project data, tracking these attributes and donation results over many years. My project will statistically analyze the DonorsChoose public datasets to identify factors that result in more (or less) effective project funding request pages. 

I want to do this project to learn how teachers could imrove the effectiveness of their crowdfunding efforts. I hope that trends and correlations can be shown that might help teachers attract more donations by creating their funding pages using the options and tactics that have roven to achieve funding completion or higher rates of donation. I could share this information to teaching communities or discussion groups for feedback, which might help others better use crowdfunding through DonorsChoose to meet their classroom expense needs. 

The DonorsChoose approach to funding education expenses is a valuable alternative for teachers who often must use personal funds to equip their classrooms or to enable novel learning experiences. Helping teachers understand the effectiveness or shortcomings of various options in setting up, describing, and categorizing their projects might increase the rates of donation, or perhaps it might produce a "zero-sum" result where some teachers become more capable at attracting donations, essentially at the expense of the other teachers using less effective project designs. Finally, my motivations are not purely altruistic as first, I intend to share my analysis with my underfunded high school-teaching wife who often funds her ideas and classrooms from our savings, typically without reimbersement from her school district. "Charity begins at home..." (Browne, 141).

## Hypotheses

1. 
2.
3.


## Data Analysis

DonorsChoose has made thirteen years of its data open and publicly accessible for analysis. The data includes information that I have downloaded and begun analysis on:

* Projects (including classroom projects that have been posted, school information such as government-issued NCES ID, lat/long, and city/state/zip)
* Donations (including donation amounts, donor city, state)
* Project resources (including materials/resources requested for the classroom projects, including vendor name)
* Project essays (including the full text of the teacher-written requests accompanying all classroom projects)
* Giving pages (number of teachers, students, amount raised)

and more, such as giftcard data which I do not intend to use.

### Option 1: Raw data

Guidelines are provided to access the full set of all their available data in CSV form at <>. 

According to the documentation, "the data is compressed, quoted, escaped and without a header. To properly import, use Python's pandas using code in 'How to read this CSV file' under each button. No need to decompress files." Each data file comes in a compressed .GZ archive, which I've extracted using WinZip for Windows.

To import the project data into Python pandas 235, for example:

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

The DonorsChoose data site provides extensive documentation for joining their data using PostGre SQL, according to this schema/ER diagram:

image

### Option 2: Pre-selected data

However, I might not tackle such SQL work to perform my analysis. Alternately, the datasets have already been decompressed, joined, and filtered into significant subsets to produce Looker visualizations. Therefore, depending upon the direction of my exploration, I might choose to download these more focused CSV files instead of the raw data discussed above.

### Option 3: API data



## License Information

## Human Centered Data Science Considerations

Crowdfunding education is positioned by DonorsChoose founder <name> as a solution. However, others consider it contrary to the democratization of decision making. (fast company). Others have concerns that DonorsChoose de-incentivizes school districts and administrations from adequately funding their schools.
  
Whether it is ultimately worthwh
  


## Works Cited

Althoff, Tim and Leskovec, Jure. "Donor Retention in Online Crowdfunding Communities: A Case Study of DonorsChoose.org." *ACM International Conference on World Wide Web (WWW)* 2015 [<https://cs.stanford.edu/people/jure/pubs/donors-www15.pdf>](https://cs.stanford.edu/people/jure/pubs/donors-www15.pdf).

Browne, Thomas. *Religio Medici : The Religion of a Doctor.* Sir Thomas Browne site: University of Chicago. Web. 21 November 2018 [<http://penelope.uchicago.edu/relmed/relmed1645.pdf>](http://penelope.uchicago.edu/relmed/relmed1645.pdf).

Tyre, Peg. "Beyond School Supplies: How DonorsChoose is Crowdsourcing Real Education Reform." FastCompany 2 October 2014: n.
pag. Web. 21 November 2018 [<https://www.fastcompany.com/3025597/donorschoose-hot-for-teachers>](https://www.fastcompany.com/3025597/donorschoose-hot-for-teachers).


●What is your plan? Describe and link to the data sources will you collect, how data will be collected and processed, the analysis you intend to perform, and the outcomes and deliverables you anticipate. 

●Are there any unknowns or dependencies that might affect your ability to complete this project? 

●How do human-centered design considerations inform... a.your decision to pursue this projectb.your approach to performing the work?

What type of data and analysis?

●Must use publicly-available and appropriately licensed dataset(s)

●Can be a ‘classic’ statistical analysis, or the design and/or evaluation of a machine learning model

●Use your own definition of ‘big data’

●Choose datasets and analyses that are likely to support reproducibility

●Choose datasets and methods that let you answer questions that you find interesting and important

●Visualizations aren’t necessary, but encouraged as an effective way of communicating your findings

You can only use a dataset for your project if the license or terms of use allow you to collect the data, analyze it, and re-publish it publicly.

●Some licenses and terms of use specifically prohibit that. 

●Some TOU say it’s okay for non-commercial purposes (like academic research). 

●Some data sources don’t specify a license or terms of use for their data (hint: avoid these).

How to document your data

When your dataset has an explicit license

1.State the license of your data (e.g. “CC-By-SA 4.0”) in your report.

2.When possible, link to the license deed, e.g. https://creativecommons.org/licenses/by-sa/4.0/

When data re-use is covered under the provider’s Terms of Use1.Quote the relevant section of the terms of use in your report2.Link to the terms of use pageIf possible, link to the original source of the data, which may be different from where you found it. 

●E.g. MovieLens data on the GroupLens website vs. MovieLens data on Kaggle

Be careful with Kaggle data

Many of those datasets are not explicitly licensed. If you cannot find appropriate license information for the data, you cannot use it. You’ll fail the assignment, even if the rest of your work is really good. :/Many of those datasets have already been analyzed by other Kagglers. Many of those analyses are public on Kaggle.com. 

●Your analysis should not simply duplicate analysis that Kagglers have already done on this dataset (e.g. “do more data scientists use Python or R?”).

●It’s perfectly fine to build off of the analysis that others have done, just make sure you cite the original analysis. 

●Tip: Avoid even looking like you might be plagiarizing someone else’s analysis. 

Talking about genderMany projects are centred on gender as a variable. Since the assignment requires you to think about ethics, consider what ‘gender’ is:

●Not the same as sex (‘man’, ‘woman’ not ‘male’, ‘female’)

●Not a binary (people have identities other than ‘man’ or ‘woman’)

●Not impermeable (people transition between genders)

●Something that creates myriad different experiences of life that are likely to be reflected in your data.

Talking about genderQuestions to ask:

●Does your data only contain binary options? If so, note that as a limitation - and note why it is a limitation (it excludes people outside that binary).

●Does your data include trans people? If so, incorporate that into the gender research. If not, highlight that as a limitation


