# Cosmetic_Chemicals_Analysis
![Intro](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/fc631681-cf11-4a3c-9b3d-ac50b4fecc7a)

## Introduction
This is a project on analysis of the chemical ingredients used in cosmetic and personal care product. 
The project is to analyze and derived insights to answer crucial questions and help know what chemicals is in your make up bags and how long the chemicals. 

** _About this dataset_**: _This dataset contains information on the chemicals used in cosmetics, including the name of the chemical, 
the company that uses it, the category of the cosmetic it is used in and the date it was reported. The dataset was downloaded from www.kaggle.com._

## Problem Statement
Do you ever wonder what ingredients are in your favorite cosmetics? Did you know that there are over 12,000 chemicals
used in cosmetics and personal care products? So what's really in your makeup bag? 
Scroll through and take a look at some of the most popular cosmetics ingredients
1.	Find out which chemicals were used the most in cosmetics and personal care products.
2.	Find out which companies used the most reported chemicals in their cosmetics and personal care products.
3.	Which brands had chemicals that were removed and discontinued? Identify the chemicals.
4.	Identify the brands that had chemicals which were mostly reported in 2018.
5.	Which brands had chemicals discontinued and removed?
6.	Identify the period between the creation of the removed chemicals and when they were actually removed.
7.	Can you tell if discontinued chemicals in bath products were removed. 


## Skills/Concept demonstrated:
MICROSOFT SQL SERVER was used and the following SQL concept were incorporated:
Select, Update, Alter, conditional filters, index, Aggregate function, CTE


#Data cleaning
There are several dirty data encountered and these are cleaned and prepared for analysis.
## _Note_: All the queries used in cleaning can be found in the uploaded "SQL_QUERIES.txt" file.
The brand name column had many inconsistencies like “Zo Skiin Health” instead of “Zo Skin Health” 
therefore correcting them using the update statement. 

![Data Cleaning 3](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/139f4698-64e4-4a39-a525-1fea148ff5a3)

![Data Cleaning 4](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/15de5bc4-d096-48d2-8e42-dd9ed0227626)



- _UPDATE SQLChemicalProject.dbo.CosmeticsChemicals_
- _SET BrandName = CASE_
- _when BrandName = '2015 WINTER COLLECTION' THEN '2015 Winter Collection'_
- _when BrandName = 'Alba Bontanica' THEN  'Alba Botanica'_
- _when BrandName = 'Couleurs Nature' THEN 'Couleur Nature'_
- _..._
* _else BrandName END;_
	
 Check the uploaded _SQL_QUERIES.txt_ file for complete scrypt.
 
--- Null rows in Brand column was changed to “Others” using Update statement

Before
     ![Data Cleaning NULL](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/01f0a3c9-683b-4b76-9678-b99ab9ce5564)

After
![Data Cleaning Others](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/95fcfd8b-e42d-4aff-8ee1-50e474eb3079)

--Dates are of different standard and I standardized the dates using the Update and CONVERT statement 
after creating columns to fill them into. 
Corrected some dates that was wrongly written like 2103 to 2013.

![Data Cleaning D1](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/cca6b8fd-3e1e-4b1f-9dc6-2d6b089df718)

--Standardize all dates
First Create new columns then populate the new column with the old column and finally delete the old columns.
**_Disclaimer_**: Do not delete the old columns if you are operating straight from the database original data.

--- Duplicated rows was checked and removed using CTE.

![Duplicates 1](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/e2f8986f-7d50-4af0-bc01-b165d4a9ca70)

## Analysis
## _Note_: All the queries used in analysis can be found in the uploaded "SQL_QUERIES.txt" file.
Q1) Find out which chemicals were used the most in cosmetics and personal care products

![pic -1 most used chemicals in cosmetics](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/f4c72350-aaf3-45a3-9a03-92b0e19ac637)

Q2) Find out which companies used the most reported chemicals in their cosmetics and personal care products.
        
![Pic 2 - Companies with most used chemicals](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/d9ae9e82-f393-4508-a908-05cd0fe6a48e)

Q3) Which brands had chemicals that were removed and discontinued? Identify the chemicals.

   ![pic 3 - brand that had their chemicals removed](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/8608979b-bce2-4b8f-b523-b13230aeb2a9)
    

Q4) Identify the brands that had chemicals which were mostly reported in 2018.
      
  ![Pic 4 - 2018 brand most reported chemicals](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/a3f56d9d-b280-48b9-bedc-4fe53a7ced16)


Q5)	Which brands had chemicals discontinued and removed? 
       
![Pic 5 - brandname discontiued](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/c8e1fa00-de56-4ff8-8b0f-39262224d6f1)


Q6) Identify the period between the creation of the removed chemicals and when they were actually removed.
     
![pic 7 - chemical active days](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/7b651700-26a1-40bf-9a59-8cf613754156)

Q7)Can you tell if discontinued chemicals in bath products were removed. 

 ![pic 8 - chemical discontinued not removed](https://github.com/Prinzeepule/Cosmetic_Chemicals_Analysis/assets/70212980/a2ce4749-521e-4c1d-b14d-779c13bfc968)
      

## Conclusion/Recommendation
- Titanium dioxide is the most used chemical in the cosmetics industries used in 85627 products.
- 100 Brands Reported Chemicals In 2018 but Only 13 of them reported above 100; The top 3 namely Zoeva repoerted 1108 Chemicals, 
Parfums Christian Dior That Reported 680 and Make Up Forever Reporting 308 Chemicals in the year under review. 
- 60 Brands Had Chemicals Discontinued And Removed. Many Chemical were discontinued but not removed.
- Chemicals discontinued should be removed as soon as possible and the dates chemicals were created or reintroduced 
should always be available as this will improve the chemical duration analysis as the case may be.
- Also, it will be good if the importance of each chemical is highlighted which will not 
only tell us the advantage of each but assist customers in choosing the best product that fits.

