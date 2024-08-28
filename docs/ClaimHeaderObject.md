These are all the fields and field types that are included as part of the claim header object in my salesforce instance

Object API Name
Claim_Header__c

Field LabelSorted Ascending	SortField Name	SortData Type	SortControlling Field	SortIndexed	Actions
Account	Account__c	Lookup(Account)		True	
Adjudicated Amount	AdjudicatedAmount__c	Currency(18, 0)		False	
Adjustment #	Adjustment_Number__c	Text(255)		False	
ChatGPT Question	ChatGPT_Question__c	Long Text Area(131072)		False	
ChatGPT Response	ChatGPT_Response__c	Long Text Area(131072)		False	
Check #	Check_Number__c	Text(255)		False	
Claim Amount	ClaimAmount__c	Currency(18, 0)		False	
Claim Number	Name	Text(80)		True	
Claim Status	ClaimStatus__c	Text(64)		False	
Coinsurance - out of Network	Coinsurance_out_of_Network__c	Currency(18, 0)		False	
Coinsurnace - In Network	Coinsurnace_In_Network__c	Currency(18, 0)		False	
Created By	CreatedById	Lookup(User)		False	
Disposition Date	Disposition_Date__c	Date		False	
External ID	ClaimNumber__c	Text(64) (External ID)		True	
External Id	ExternalId__c	Text(255) (External ID)		True	
Fill Date	Fill_Date__c	Date		False	
Last Modified By	LastModifiedById	Lookup(User)		False	
Medicare	Medicare__c	Text(255)		False	
Notes	Notes__c	Long Text Area(32768)		False	
Owner	OwnerId	Lookup(User,Group)		True	
Payment Status	Payment_Status__c	Text(255)		False	
Provider	Provider__c	Text(255)		False	
Provider Id	Provider_Id__c	Text(255)		False	
Provider NPI	Provider_NPI__c	Text(255)		False	
Provider Type	Provider_Type__c	Text(255)		False	
Service Description	Service_Description__c	Text(255)		False	
Status Reason	Status_Reason__c	Text(255)		False	
Submitted On	SubmittedOn__c	Date		False	
Total Applied to Deductible	Total_Applied_to_Deductible__c	Currency(18, 0)		False	
Total Eligible	Total_Eligible__c	Currency(18, 0)		False	
Total Paid	Total_Paid__c	Currency(18, 0)		