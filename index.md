# Project
## Week 6 part 1 
   ## Import the survey data 
   - From NAHNES, download 1999-2000 National Health and Nutrition Examination Survey
> Stata command 
 ```stata
 import sasxport5 \"https://wwwn.cdc.gov/Nchs/Nhanes/1999-2000/DEMO.XPT\"
 ```
   ## Obtain mortality followup data
   - From this [link](https://ftp.cdc.gov/pub/) click:
      - Health Statistics
         - NCHS
            - Datalinkage
               - Linked Mortality
               - Download:
                 `NHANES_1999_2000_MORT_2019_PUBLIC.dat`
                 `Stata_ReadInProgramAllSurveys.do`
               
   - Open a .do file and run the following command: 
> Stata command
```stata
 //data
 global mort_1999_2000 https://ftp.cdc.gov/pub/HEALTH_STATISTICS/NCHS/datalinkage/linked_mortality/NHANES_1999_2000_MORT_2019_PUBLIC.dat

 //code
cat https://ftp.cdc.gov/pub/HEALTH_STATISTICS/NCHS/datalinkage/linked_mortality/Stata_ReadInProgramAllSurveys.do
```

   ## Development 
   ### Edit and rename 
   - Upload `Stata_ReadInProgramAllSurveys.do` to your repo
   - Rename this file to followup.do and commit it with the description: “Updated DEMO.XPT linkage .do file”.
   ```stata
   //use your own project repo 
   global repo "https://github.com/hyomin295/project"
   do ${repo}followup.do
   save followup, replace
   ```

   ### Merging 
   - merge the survey data to mortality followup data 
   ```stata
   import sasxport5 "https://wwwn.cdc.gov/Nchs/Nhanes/1999-2000/DEMO.XPT", clear
   merge 1:1 seqn using followup
      //this ensures the alignmnet of the unqiue sequence
   lookfor follow
   ```
