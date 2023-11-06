1 TB - Each 100 MB, 1 GB = 10 files
     = 10000 files

/data [without partition]
    file1.parquest
    ..
    file10000.parquet


Country=IN [200 GB]
  Year=2022 [40 GB]
    Month....[4 GB]
       Day...[200 MB]
  Year=2023
     Month=01 
        Day=26


Country=USA [300 GB]
  Year=2023
     Month=01 
        Day=26

Country=UK [10 GB]
  Year=2023
     Month=01 
        Day=26


SELECT .. GROUP BY ... WHERE Country='IN'


SELECT .. GROUP BY COUNTRY, YEAR ..


SELECT .... HAVING 

SELECt .... from table; [with/without partition], no WHERE clause
    READ 1 TB 
    process 1 TB data


SELECt .... from table where Country=IN; [without partition] 
    READ 1 TB 
     project/SELECT 200 GB Data from India
     800 GB data will be discarded after processing 
       Time
       CPU
       Cost money for computing
       Additional compute resources
       +
       Databricks DBU costs
    process 1 TB data


SELECT .... from table where Country=IN; [with partition]

    Reads only 200 GB
    Cost saving
    Time saving


SELECT .... from table where Country=IN and Year=2022; [with partition]

    Reads only 40 GB
    Cost saving
    Time saving

