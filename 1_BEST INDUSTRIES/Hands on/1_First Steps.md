### What are we looking for?

For this project the goal is to get to know the best three industries to work at in México.

### Extracting Data

The information used in this analysis can be found in the INEGI website, which is a government website with a lot of useful datasets about México. As we want to learn more about the manufacturing industry, lets download a data set containing data related to the quantity of hours worked in a day by his employees and other useful informations for our means.

https://www.inegi.org.mx/datosabiertos/

#### Selected dataset:

>> **Subsistema de Información Económica/Históricas/Encuestas/ Encuesta Anual de la Industria Manufacturera**
<div align="center">
    <img src="https://i.ibb.co/VHqfPDw/1-1-INEGI.png">
</div>

I choosed this dataset because it contains information about the numbers of employees per industry, worked hours, how much worth does a certain industry produces with his own raw material, etc. 


### Exploring Data

We got a .zip file from the site, this file has five directories. After looking into those directories I substracted three files that contains useful data. 

 - **conjunto_de_datos\tr_eaim_cifra_2013_2017.csv:**
    
    - Shape: 1740x37,
    - KeyColumn: 'CODIGO_SCIAN'
    - mainly int numbers data with one string type column,
    - mainly alphanumerical column headers,
    - it's impossible to deduce the meaning of the column headers without additional information.
 - **diccionario_de_datos\diccionario_de_datos_tr_eaim_cifra_2013_2017.csv**

    - Shape: 348x2,
    - Key Column: 'CODIGO_SCIAN',
    - String type columns,
    - Meaning of the codes from 'CODIGO_SCIAN' column,
    - The number of digits indicates the herarchy of the industry, beign:
        - 31-33 All manufacturing industries.
        - Three digit code, subcategory of manufacturing industry, say: 311 - Alimentary Industry, 321 Wood Industry.
        - And so on, every additional digit in this code represents a new subcategory of a specific industry.
 - **catalogos\tc_scian.csv**

    - Shape: 38x5,
    - Key Column: 'COLUMNA',
    - String type columns,
    - Column headers and their meaning.

The next step is going to be cleaning the data using python and the famous pandas library.