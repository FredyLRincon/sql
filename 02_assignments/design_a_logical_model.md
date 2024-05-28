# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

[Small_Bookstore_ERD](SmallBookstoreSQLAssignment_1.png)

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

[EmployeeShifts](EmployeeShifts.png)

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

[CustomerAddressesOverwriteVsRetain](CustomerAddress(OverwriteVsRetain).png)

Architectures for CUSTOMER_ADDRESS Table
Type 1: Overwrite Changes
The following design overwrites the address whenever there is a change:

CustomerAddress
AddressID (Primary Key)
CustomerID (Foreign Key)
AddressLine1
AddressLine2
City
State
PostalCode
Country


Type 2: Retain Changes
The following design retains the historical addresses by storing the start and end dates:

CustomerAddress
AddressID (Primary Key)
CustomerID (Foreign Key)
AddressLine1
AddressLine2
City
State
PostalCode
Country
StartDate
EndDate (It indicates the current address when null)

_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
Yes, there are privacy implications. Storing historical addresses can lead to privacy concerns, especially if the data needs to be handled properly. It could expose customers' previous residences, which is sensitive information.

```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
1. Complexity and Scope
   - AdventureWorks schema is more complex with many more entities, including detailed tables for functions like 'Production', 'Sales', 'HumanResources', etc. The bookstore schema is much simpler, focusing on core entities like employees, orders, sales, customers, and books.

2. Normalization
   - AdventureWorks schema is highly normalized with many relationships and reference tables. The bookstore schema is relatively straightforward, with fewer tables and relationships, focusing on essential business functions.

3. Reflection
The differences highlight the varying needs and scales of businesses. AdventureWorks is designed for a larger, more complex organization, whereas the model for the bookstore is simpler and more suitable for a smaller company. If the bookstore grows, it may require additional tables and normalization similar to AdventureWorks to manage complexity effectively.
```

# Criteria

[Assignment Rubric](./assignment_rubric.md)

# Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `June 1, 2024`
* The branch name for your repo should be: `model-design`
* What to submit for this assignment:
    * This markdown (design_a_logical_model.md) should be populated.
    * Two Entity-Relationship Diagrams (preferably in a pdf, jpeg, png format).
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sql/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [X] Create a branch called `model-design`.
- [X] Ensure that the repository is public.
- [X] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [X] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
