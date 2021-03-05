# Assignment Summary 
##Thank you for giving me a chance to work on this assignment

This assignment involves data wrangling of 3 csv files and loading it to Zendesk system.
I have used Python as the programming language and used Pandas Dataframe as the main DS.

For Zendesk Authentication, I have generated a Token from Dashboard and used Basic Authentication method in all API requests.

I started with Organizations File, domain_names field required some transformation as it contains both single valued and multi-valued list.
After loading a row in Zendesk system, I took the id generated and saved it in org_df dataframe which would be required later.

Then comes the Users File, here we have organization_id which is not relevant to our newly inserted org records and thus I had to map old values with new ones.
I found rows with duplicate emails and since Zendesk system allows Users with unique mail id, I had to drop duplicatge rows.
For Bulk Loading, I created a batch of 100 rows and then posted to the API. 
Since with Bulk loading I couldn't find a way to get the new user id for each row that has been processed, I later had to fetch the list from API by using external_id. (I passed the old user id for external_id so that later I can get the mapping for old and new user id)

Finally with Tickets File, I fetched old and new user id mapping from the users API. Then I used the mapping to substitute the old requester, assignee and submitter id with the new user id.
I also ensured that valid ticket status is loaded to system by mapping old status with new ones.
For loading tickets to Zendesk, I created a batch of 100 rows and since here we have a Rate Limit for rows to be uploaded I retried my request after waiting for 120 seconds.

There could be some discrepancies with the data loaded by me as I was running short of time to test it thoroughly.
It was an amazing experience to actually face the data wrangling issues and I took this assignment as a challenge and I hope it turns out to be good for me. 


