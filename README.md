# Streamlining IT Procurement: Automating Standard Laptop Orders with Flow Designer

## Problem Statement

The current IT procurement process lacks efficiency and automation,
resulting in delays and manual overhead, particularly in handling
standard laptop orders. Requests for standard laptops often require
configuration, but this step is prone to oversight or delay, leading to
frustration among users and inefficient resource allocation within the
IT department.

## User Story

As a member of the IT procurement team, I want a streamlined process for
ordering standard laptops so that tasks are automatically generated and
assigned to the hardware team for configuration. This will ensure that
laptops are promptly configured upon arrival, reducing user wait times
and minimising manual intervention.

## Project Objective

The objective of this project is to implement an automated workflow
using **Flow Designer** to facilitate the procurement and configuration
of standard laptops.

The project aims to:

1.  Create a seamless experience for users requesting standard laptops
    by ensuring timely configuration.
2.  Reduce manual intervention and potential errors in the procurement
    process.
3.  Improve resource utilisation within the IT department by optimising
    task allocation.
4.  Enhance overall efficiency and productivity in IT procurement
    operations.

## Milestone 1: Flow

### Activity 1: Create a Flow

Create a Flow to create a Catalog Task, update the short description
after approval of the Service Request, and assign the task to the
**Hardware** group.

### Steps

1.  Open ServiceNow.
2.  Click **All** and search for **Flow Designer**.
3.  Click **Flow Designer** under **Process Automation**.
4.  Click **New** and select **Flow**.
5.  Under Flow Properties:
    -   **Flow Name:** `Standard laptop task`
    -   **Application:** `Global`
    -   **Run As:** `System user`
6.  Click **Submit**.
7.  Click **Add a trigger**.
8.  Search for and select **Service Catalog**.
9.  Click **Done**.
10. Under **Actions**, click **Add an action**.
11. Search for and select **Create Catalog Task**.
12. Configure the action:
    -   **Action:** Create Catalog Task
    -   **Request item:** Drag and drop the **Requested Item Record**
    -   **Table:** Automatically populated as **Catalog Task**
    -   **Short description:** `Laptop need to Configured`
13. Click **Add field value**.
14. Configure:
    -   **Description:** `Laptop need to Configured`
    -   **Assignment group:** `Hardware`
    -   **Approval:** `Approved`
15. Leave the remaining fields as default.
16. Click **Done**.
17. Click **Save** the Flow.
18. Click **Activate**, then click **Activate** again.

## Milestone 2: Flow Assignment

### Activity 1: Assign the Flow to the Standard Laptop Service Catalog

1.  Open ServiceNow.
2.  Click **All** and search for **Maintain Items**.
3.  Select **Maintain Items**.
4.  Under the **Name** field, search for **Standard Laptop** and select
    the record.
5.  Under the record, select **Process Engine**.
6.  Remove the remaining automations and add **Flow**.
7.  Add the Flow created earlier with the name **Standard Laptop Task**.
8.  Click the menu to save the record.

## Milestone 3: Service Catalog

### Activity 1: Place the Standard Laptop Order and Get Approval

1.  Click **All** and search for **Service Catalog**.
2.  Click **Service Catalog** and then click **Hardware**.
3.  Scroll to find **Standard Laptop** and select it.
4.  Click **Order Now** to place the request.
5.  View the **Order Status**.
6.  Click the **Request Number**.
7.  The Requested Number record will open.
8.  Scroll down to the **Approvers** section.
9.  Right-click the record, open the configuration options, and click
    **Approve**.
10. Click the **Requested Item** section.
11. Open the Requested Item record.
12. Scroll down to the **Catalog Tasks** section.
13. Open the Catalog Task record to view the updated status, short
    description, and assigned group.

## Workflow Summary

``` text
User orders Standard Laptop
            ↓
      Service Catalog
            ↓
       Approval
            ↓
       Flow Trigger
            ↓
   Create Catalog Task
            ↓
 Assignment Group: Hardware
            ↓
 Laptop configuration task
```

## Conclusion

By automating the standard laptop procurement process with ServiceNow's
**Flow Designer**, the project effectively addresses inefficiencies and
reduces manual overhead. This streamlined workflow ensures timely
configuration of laptops, minimises user wait times, and enhances
overall productivity within the IT department.

The automated solution also optimizes resource allocation and improves
the user experience by providing a seamless and efficient procurement
process.

## Technologies Used

-   ServiceNow
-   Flow Designer
-   Service Catalog
-   Catalog Tasks
-   Process Automation
-   Hardware Assignment Group
