# Assignment 1: Design a Logical Model

## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

### Answer:

DIAGRAM:

![Assignment_Question_1_Bookstore_Relational_Database_Model.drawio.png] (./03_homework/images/Assignment_Question_1_Bookstore_Relational_Database_Model.drawio.png)
 
 
LINK:

[Assignment_Question_1_Bookstore_Relational_Database_Model.drawio.png] (https://github.com/cavengal/sql/blob/99898df52bb38aa3b2085720b3b91fbd2f4f7548/03_homework/images/Assignment_Question_1_Bookstore_Relational_Database_Model.drawio.png)


## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

### Answer:

DIAGRAM:

![Assignment_Question_2_Expanded_Bookstore_Relational_Database_Model.drawio.png] (./03_homework/images/Assignment_Question_2_Expanded_Bookstore_Relational_Database_Model.drawio.png)
 
 
LINK:

[Assignment_Question_2_Expanded_Bookstore_Relational_Database_Model.drawio.png] (https://github.com/cavengal/sql/blob/99898df52bb38aa3b2085720b3b91fbd2f4f7548/03_homework/images/Assignment_Question_2_Expanded_Bookstore_Relational_Database_Model.drawio.png)

## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

### Answer:

DIAGRAM:

![Assignment_Question 3_Bookstore_Customer_Address_Table_Architectures.drawio.png] (./03_homework/images/Assignment_Question 3_Bookstore_Customer_Address_Table_Architectures.drawio.png)
 
 
LINK:

[Assignment_Question 3_Bookstore_Customer_Address_Table_Architectures.drawio.png] (https://github.com/cavengal/sql/blob/99898df52bb38aa3b2085720b3b91fbd2f4f7548/03_homework/images/Assignment_Question%203_Bookstore_Customer_Address_Table_Architectures.drawio.png)


_Hint, search type 1 vs type 2 slowly changing dimensions._

Bonus: Are there privacy implications to this, why or why not?
```
In the Type 1 Architecture, old addresses are overwritten, which limits exposure of historical data, greatly reducing privacy concerns. Meanwhile in the Type 2  Architecture, there is a greater volume of historical personal information stored, which could be more susceptible to breaches or misuse.

This does not mean that Type 2 SCD should not be implemented, but it would mean that if the bookstore chooses this option, it must be ready to assume the costs of adding data access and protection measures and comply with the regulatory framework governing data retention, data access, the right to be forgotten among others
```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
The first major difference I see relates to the scale of the businesses and the data needs of each one. The AdventureWorks ERD reflects a database suited for a larger scale company that produces and sells various products in distinct categories. This adds the need for more complex production, purchasing, HR, customer, and sales tables compartmentalized by business area to effectively track all steps of the production-to-sale cycle for such a company. A small bookstore may not need such a large-scale database but could definitely add the comprehensive granularity level of the AdventureWorks database for the relevant common business areas that it contains: HR, customer, purchasing and Sales.

The second major difference that I noticed is that the tables in AdventureWorks are much more broken down and are mostly set up for Type 2 Slow changing dimensions by having a field for ‘ModifiedDate’ that allows to keep historical records for changes in the tables which facilitates future analysis of all the records and transactions in each area. 

For the bookstore ERD one major thing that I would have done differently is adding PURCHASING tables to keep track of the stock units and the value (cost) of the book inventory and allowing this information to better connect with the company’s bookkeeping activities. I would have also added the possibility for one sale to contain more than one order of books. I contemplated the possibility of one order containing several books for sure, but not the possibility that one sale could contain several orders.

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
