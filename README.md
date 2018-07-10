# pySpark-flatten-dataframe
PySpark function to flatten any complex nested dataframe structure loaded from JSON/CSV/SQL/Parquet

For example, for nested JSONs -

*   Flattens all nested items:
{
"human":{
    "name":{
        "first_name":"Jay Lohokare"
      }
   }
}

Is converted to dataFrame with column = 'human-name-first_name'
The connector '-' can be changed by changing the connector variable.


*   Explodes Arrays:
{
"array":["one", "two", "three"]
}
Is converted to dataFrame with column = 'array' with 3 rows
<br><br>

The function can handle any level of nesting.

The function can <b>NOT</b> handle Arrays within Arrays. 
This is just to keep the code dynamic and generic. To handle Arrays within Arrays, modify ```
if isinstance``` in the ```for``` loop of ```flattenSchema``` function
