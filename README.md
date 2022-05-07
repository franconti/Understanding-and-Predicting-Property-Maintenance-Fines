# Understanding-and-Predicting-Property-Maintenance-Fines



INTRODUCTION:

This project is about a busnies problem related to Detroit’s blight complication.
Blight is a term used to signify property or land that is in poor condition due to a lack of upkeep and maintenance. As a result, the property eventually becomes unsafe or uninhabitable. As a solution, the goverment started issuing maintenance fines to residents and owners of the respective properties. 
Because most of blight tickets were not paid, the aim of this project was to predict blight compliance and understand why the rate of compliance was so low. 

THE OBJETIVE: 

The objetive is to predict whether a given blight ticket will be paid on time.


DATA:

There are two data files for use in training and validating the models: train.csv and test.csv. Each row in these two files corresponds to a single blight ticket, and includes information about when, why, and to whom each ticket was issued. The target variable is compliance, which is True if the ticket was paid early, on time, or within one month of the hearing data, False if the ticket was paid after the hearing date or not at all, and Null if the violator was found not responsible. Compliance, as well as a handful of other variables that will not be available at test-time, are only included in train.csv.

File descriptions (Use only this data for training your model!)
readonly/train.csv - the training set (all tickets issued 2004-2011)
readonly/test.csv - the test set (all tickets issued 2012-2016)
readonly/addresses.csv & readonly/latlons.csv - mapping from ticket id to addresses, and from addresses to lat/lon coordinates. 
 Note: misspelled addresses may be incorrectly geolocated.
 
 
     Data fields:
       
       
      train.csv & test.csv:
      
        ticket_id - unique identifier for tickets
        agency_name - Agency that issued the ticket
        inspector_name - Name of inspector that issued the ticket
        violator_name - Name of the person/organization that the ticket was issued to
        violation_street_number, violation_street_name, violation_zip_code - Address where the violation occurred
        mailing_address_str_number, mailing_address_str_name, city, state, zip_code, non_us_str_code, country - Mailing address of the violator
        ticket_issued_date - Date and time the ticket was issued
        hearing_date - Date and time the violator's hearing was scheduled
        violation_code, violation_description - Type of violation
        disposition - Judgment and judgement type
        fine_amount - Violation fine amount, excluding fees
        admin_fee - $20 fee assigned to responsible judgments
        state_fee - $10 fee assigned to responsible judgments
        late_fee - 10% fee assigned to responsible judgments
        discount_amount - discount applied, if any
        clean_up_cost - DPW clean-up or graffiti removal cost
        judgment_amount - Sum of all fines and fees
        grafitti_status - Flag for graffiti violations
        
        
      train.csv only:
      
        payment_amount - Amount paid, if any
        payment_date - Date payment was made, if it was received
        payment_status - Current payment status as of Feb 1 2017
        balance_due - Fines and fees still owed
        collection_status - Flag for payments in collections
        compliance [target variable for prediction] 
         Null = Not responsible
         0 = Responsible, non-compliant
         1 = Responsible, compliant
        compliance_detail - More information on why each ticket was marked compliant or non-compliant



DATA CLEANING 

After a look of the variables were removed Variables that contained payment information, Variables  with too many missing/null values, Variables that contained too many categories. 

Number of unique values in violation_code: 235
Number of unique values in violation_description: 258
Number of unique values in violation_street_name: 1791
Number of unique values in disposition: 9
Number of unique values in zip_code: 5643
Number of unique values in inspector_name: 173




