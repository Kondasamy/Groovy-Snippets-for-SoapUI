# DATE ::  Get First day & Last day of the current Year #

## Problem Statement: ##
We might face some scenarios, where we need to validate our actual result with first day and last day of the year. We might hard code the First day and Last Day of the year, but we face the situation on manually changing the dates every year.

## Resolution: ##
In order to solve this problem, we could utilize the **"SimpleDateFormat"** class provided by Java and assert the result with actual result.

## Prerequisite: ##
1. Create a Groovy Script assertion/ Groovy Script Test step within the test step
1. Paste the below code and run it

## Code Snippet ##
    import java.text.SimpleDateFormat
    
    Calendar c = Calendar.getInstance();  
    
    //Calculate and Print LAST day of the year
    c.set(Calendar.DAY_OF_YEAR,  c.getActualMaximum(Calendar.DAY_OF_YEAR));  
    SimpleDateFormat last = new SimpleDateFormat("dd/MM/yyyy")  
    log.info "Last day of the Year: " + last.format(c.getTime()) 
    
    //Calculate and Print FIRST day of the year
    c.set(Calendar.DAY_OF_YEAR,  c.getActualMinimum(Calendar.DAY_OF_YEAR));  
    SimpleDateFormat first = new SimpleDateFormat("dd/MM/yyyy")  
    log.info "First day of the Year: " + first.format(c.getTime())
    
    **Script Log:**
    Tue Dec 16 14:59:22 IST 2014:INFO:Last day of the Year: 31/12/2014
    Tue Dec 16 14:59:22 IST 2014:INFO:First day of the Year: 01/01/2014