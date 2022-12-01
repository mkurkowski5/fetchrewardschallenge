# fetchrewardschallenge

Hello recruiter!

Thanks for taking the time to review my Data Analyst coding exercise responses.  
I've kept things as straightforward as possible in this repo, so you should be able to find each requirement's response in a separate location.

For the first requirement, you can download a pdf of the relational diagram I've built in the Issues tab above.  
If you have any issues accessing or viewing it, please email me (mkurkows@alumni.nd.edu) and I will forward it to you asap.
The idea here is to keep things simple and accessible, with relevant data together.  
  - the 'Users' data are already pretty succinct, and can be referenced from Receipts
  - 'Brands' contains two columns that explicitly reference other columns, 'brandCode' and 'categoryCode', so I put their references into separate 
      files, one with product data, 'Products', and one with category data, including the 'category' column, 'Categories'
  - 'Receipts' was clearly the largest data file in terms of columns, and the hinge upon which all the other data are connected, so I broke it out into 
      three general groupings: 'Points' which contained all things related to rewarding points including bonus points (dates, etc.), 'Purchases' which 
      held all purchase data on the receipt, and I kept 'Receipts' which references the other two and has a unique id for each entry
  - 'Receipts.userId' references 'Users._id'
  - (new) 'Receipts.pointsId' references (new) 'Points._id'
  - (new) 'Receipts.purchaseId' references (new) 'Purchases._id'
  - 'Purchases.rewardsReceiptItemList' should contain at least one barcode which references 'Brands.barcode'
  - 'Brands.brandCode' references 'Products.brand' (requirement constraint)
  - 'Brands.categoryCode' references 'Categories.BrandCategory' (requirement constraint)

The rest of the requirements each have a separate "Code" file (the fourth requirement isn't really code).

For the second requirement, I've included a file called "Second", which targets the middle two business questions (concerning "Accepted" or "Rejected"
  receipt statuses).  
I chose to focus on these, because the SQL query was clean and straightforward.  
Initially I built a query to answer the first question or two (and would have expanded to capture the last two as well), but I wasn't able to quickly 
  identify an elegant way to parse the month value from the date, and I understand that you're looking for Data Analysts sooner than later.

For the third requirement, I also took a "What's the quickest way I can obtain meaningful information from the data (that I can then investigate in 
  greater detail in a real-world scenario) ?" approach.
This led me to focus on essential data values that, if missing, would render a table entry fairly irrelevant to the majority of business functions 
  (things like knowing what items or amount a receipt was for, or identifying missing barcodes that would be needed to join to a separate Brands table,
  for instance).

And finally, I tackled the fourth requirement as if I were communicating with someone on the business ops side, so that they would have a clearer 
  understanding of the types of data relationships we can know at this time, what would need to happen if we wanted to know other ones, and what some 
  suggestions would be for scaling going forward.

Thank you for your time,
Michael Kurkowski
