## Welcome to the Virtual Worker (Just testing about)

Norbert, also known as the virtual worker, is a virtual assistant that handles incoming emails for West & North Northants Council. Norbert will log them within the customer services record management system and either resolve the query with a suitable response or redirect the enquiry to someone who can review and respond.

Norbert is able to answer frequently ask questions received by their customer, enabling that 24/7 support. This includes re-direction to online services available on the authority website, as well as re direction to other sovereign authority websites, partners and organisations.

This removes the need for a customer services agent to resolve simple queries requiring an almost “pre-packaged” response and enables the customer to get an almost simultaneous reply, freeing up agents to spend their time on resolving more complex issues that require that dedicated time. 
### [Documents](https://wnugov.sharepoint.com/sites/FNP-Digital/Shared%20Documents/Mail%20Automation%20Project)
### [Report An Issue or Share an Idea](https://github.com/FutureNorthants/VirtualWorker/issues/new/choose)
<img width="909" alt="Screenshot 2021-11-12 at 09 27 29" src="https://user-images.githubusercontent.com/78955180/141443921-cf7274ac-1cb3-4985-b80d-1d2b329f0df7.png">
Norbert supports with all emails that are recieved at contactus@northnorthants.gov.uk, contactus@westnorthants.gov.uk and through the contact us forms for North and West Northants. 

### Current Sprint - https://github.com/FutureNorthants/VirtualWorker/projects

# Testing Emails/URL's

* contactus-test@northampton.digital - Northampton's MailBot Functionality
* documents-test@northampton.digital - Northampton's Bundler Functionality 
* unitary-test@northampton.digital - West Northamptonshires Unitary UAT Email Functionality
* [West Northants Contact Us Form](https://northamptonshire-self.test.achieveservice.com/service/Contact_West_Northamptonshire_Council) - Wests UAT Contact Us Form
* [West Northants UAT](https://northamptonuat.q.jadu.net/q/login) - Wests UAT Jadu System
* [Guildhall Contact Us Form](https://uat.northampton.gov.uk/xfp/form/202) - Guildhalls UAT Contact Us Form

# MailBot Sovereign Forward OutPuts (Amazon Lex)

Lex Intents are "service areas" or departments that are built within the Amazon Lex System.

The Lex Intents/Service Areas hold "utterances", also known as Key Phrases. These are key phrases or words that are connected to that service.
For example the key phrase "bin" will be apart of the Lex Service Waste and Reycling. 

Norbert uses these utterances (Key phrases) to ascertain the intent (Service Area/Department) 

Once Norbert has set a service area, he can check the Dynamo DataBase to ascertain the email address for that Intent (Service Area) for the outlined Soverign Council.



| Lex Intents |                                                            
| --- | 
| `Adoption` 
| 'Adult Learning' |
| 'Adult Social Services' |
| 'Blue Badge' |
| 'Bus Passes' |
| 'Child Safe Guarding' |
| 'Early Years' |
| 'Fines' |
| 'Fostering' |
| 'Heritage History and Archives
| 'Highways' |
| 'libraries' |
| 'Parks' |
| 'Registrars' |
| 'School Admissions' |
| 'School Meals' |
| 'School Transport' |
| 'Street Light' |
| 'Trading Standards' |
| 'County Waste' |
| 'Abandoned Vehicles' |
| 'Allotments ' |
| 'Benefits' |
| 'Building Control' |
| 'Business Rates' |
| 'Call Care' |
| 'Cemeteries' |
| 'Covid' |
| 'Democratic Services' |
| 'Dog Services' |
| 'Elections' |
| 'Environmental Health and Protection' |
| 'Events' |
| 'Fly Tipping' |
| 'Freedom of Information' |
| 'Garden Services' |
| 'Housing Applications' |
| 'Housing Options' |
| 'Housing Repairs' |
| 'Jobs' |
| 'Land Charges' |
| 'Leisure' |
| 'Licensing' |
| 'Parking' |
| 'Planning' |
| 'Private Sector Housing' |
| 'Repairs' |
| 'Revenues' |
| 'Street Cleansing' |
| 'Tenancy Management' |
| 'Waste' |


To increase Norberts confidence score on correctly ascertaining the Soverign Service Area, adaptions have been made to his functionality when dealing with contact us forms. 

As the customer is telling Norbert the service they require, Norbert doesn't have to do as much work. However, in some instances there is a broader "sub categories" that fall within that service. For instance Housing is an over-arch of Housing Applications, Housing Solutions & Options, Tenancy Management, Repairs, Private Sector and much more.

In light of this - there are some areas where Norbert already knows the overarching service area; or in Amazon Lex terms the intent. So Norbert is able to already link the customers enquiry; or in amazon Lex terms the utterance. 

We tell Norbert to "ignore all he knows" in certain areas. These are highlighted below in their intent format. 

For example if a customer selects Adult Social Care - Norbert will set the service intent (service area outcome) to that field.

If the table outlines Lex, think means we have asked Norbert to read his knowledge database and find the utterance (customer query) that best matches to that Intent (Service Area). He will return what ever he finds as the best match, which is what is used to define the Soverign Service Area. 



| Service Area | Lex Database or Specific Intent |
| --- | --- |
| `Adult Social Care` | County_AdultSocialServices |
| `Benefits` | District_Benefits |
| `Births, Marriages & Death Registration Service` | County_Registrars |
| `Blue Badges` | County_Registrars |
| `Business Rates` | District_BusinessRates |
| `Building Control` | District_BuildingControl |
| `Children's Social Care` | County_ChildSafeGuarding |
| `Coronavirus` | District_Covid |
| `Council Tax` | District_Revenues |
| `Environmental Issues` | **Lex** |
| `Housing` | **Lex** |
| `Libraries` | County_Libraries |
| `Parking` | District_Parking |
| `Planning` | **Lex** |
| `Roads and Highways` | County_Highways|
| `School Admissions and Schools` | County_SchoolAdmissions|
| `Transport` | County_SchoolTransport|
| `Waste and Recycling` | **Lex** |
