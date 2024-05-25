# Assignment 1: Design a Logical Model
By Hui Li
## Question 1
Create a logical model for a small bookstore. 📚

At the minimum it should have employee, order, sales, customer, and book entities (tables). Determine sensible column and table design based on what you know about these concepts. Keep it simple, but work out sensible relationships to keep tables reasonably sized. Include a date table. There are several tools online you can use, I'd recommend [_Draw.io_](https://www.drawio.com/) or [_LucidChart_](https://www.lucidchart.com/pages/).

![image](https://github.com/littlehappy93/sql/assets/167244237/4b5f0586-ed77-47a9-ab4b-3f65797a3872)

## Question 2
We want to create employee shifts, splitting up the day into morning and evening. Add this to the ERD.

![image](https://github.com/littlehappy93/sql/assets/167244237/f308c222-5ef4-4280-8011-1f1c878e6caf)


## Question 3
The store wants to keep customer addresses. Propose two architectures for the CUSTOMER_ADDRESS table, one that will retain changes, and another that will overwrite. Which is type 1, which is type 2?

_Hint, search type 1 vs type 2 slowly changing dimensions._

Type 1: Overwrite
customer_id (Primary Key, Foreign Key)
address_line1
address_line2
city
province
post_code
country

Type 2: Retain Changes
address_id (Primary Key)
customer_id (Foreign Key)
address_line1
address_line2
city
province
post_code
country
start_date (Effective from date)
end_date (Effective to date, NULL if current)


Bonus: Are there privacy implications to this, why or why not?
```
Your answer...
Type 1 is mnimal privacy implications as store only retaines the current address.
Type 2 is higher privacy implications as store retains whole historical addresses which could offence customers' privacy right. 
```

## Question 4
Review the AdventureWorks Schema [here](https://i.stack.imgur.com/LMu4W.gif)

Highlight at least two differences between it and your ERD. Would you change anything in yours?
```
Your answer...
1. The ERD is highly detailed, with each table containing numerous branches and categories. The main categories are highlighted in different colors and include additional explanatory notes. This design makes it easy for readers to understand the ERD and its underlying logic.
2.There are clear arrows between the tables, and the primary keys (PK) and foreign keys (FK) are clearly indicated under each table.
I will add the PK/FK and efficient arrow in my 2 ERD
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
- [ ] Create a branch called `model-design`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via our Slack at `#cohort-3-help`. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.
