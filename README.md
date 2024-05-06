# Project
## Week 6 part 1 
   ## Import the survey data 
   - from NAHNES, download 1999-2000 National Health and Nutrition Examination Survey
> Stata command 
 ```stata
 import sasxport5 \"https://wwwn.cdc.gov/Nchs/Nhanes/1999-2000/DEMO.XPT\"
 ```
   ## Obtain mortality followup data
   - from this [link](https://ftp.cdc.gov/pub/) click:
      - Health Statistics
         - NCHS
            - Datalinkage
               - Linked Mortality
               - Download:
                 `NHANES_1999_2000_MORT_2019_PUBLIC.dat`
                 `Stata_ReadInProgramAllSurveys.do`
> Stata command
```stata
 //data
 global mort_1999_2000 https://ftp.cdc.gov/pub/HEALTH_STATISTICS/NCHS/datalinkage/linked_mortality/NHANES_1999_2000_MORT_2019_PUBLIC.dat

 //code
cat https://ftp.cdc.gov/pub/HEALTH_STATISTICS/NCHS/datalinkage/linked_mortality/Stata_ReadInProgramAllSurveys.do
```

   ## Development 
   ### Edit and rename 
   - Upload the provided Stata .do 
   - Rename this file to followup.do and commit it with the description: “Updated DEMO.XPT linkage .do file”.
     

   ### Merging 
