## **Doc Intel Lab**

<br />

## Introduction

Document Intelligence is a machine learning (ML) solution that provides assistance to quickly and accurately extract information from documents to the Now Platform® enabling you to quickly process highly variable documents that change over time.

Many organizations today use simple optical character recognition (OCR) solutions to extract data from documents that requires significant manual configuration, and also often requires manual changes as the documents evolve. Document Intelligence extends beyond the simple OCR by using ML to identify, understand, and extract text and data from documents. This enables you to accurately automate document processing and accurately extract information from documents, even when the documents have varied text, data, and templates.

We added this capability on the platform so the data extraction from documents can easily be done but also for our customer to be able to do this from within their own Workflows on the platform. A lot of processes still involve digital documents, this can be a useful capability as organisation are progressing on their hyperautomation journey.

<br />
<br />


## Goal

In this lab, we will configure Doc Intel to automate the extraction of data from a physical form of identification (Driver's License, Government Issued ID, Passport, etc.) in order to drive efficiency.

<br />
<br />


## Use Case

ACME Inc. has a mandate to automate as much as possible within their organization to drive efficiency, reduce costs, and improve user experience. They have identified their current 'Visitor Access' process as highly repetitive and time consuming for their agents. In the current process, agents receive visitor information via email and need to manually enter it into the Badging Application to print a visitor's badge.


As a member of ACME Inc.'s Automation Center of Excellence, you have been contacted to automate the task of a collecting visitor information, from their driver’s license or other form of physical identification, in order to streamline the process and reduce manual efforts.

<br />
<br />


## Doc Intel Admin Workspace

The Doc Intel Admin Workspace is built on the Next experience and provides process owners with an easy way to set up, configure, and monitor their document processing solutions.

1. Login to your instance as **Admin**

2. Navigate to **All > Document Data Extraction Administration > Home** to view the workspace and begin configuring a Doc Intel Use Case.

On the Home tab, the dashboard provides a quick glance at Doc Intel performance for selected Use Cases, as well as helpful resources to get started:


<img width="1915" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/9b7013cd-fd91-48cc-b0cc-c3c4c3f2a72d">


>Note:
>
> - Accuracy of Extraction (%): Based on the number of times the AI's top recommendation is the correct answer(accuracy is expressed as a percentage (%))
>
> - Agent effort (Avg. KPET): Based on the number of Keystrokes an agent performs to extract all field values(measured in Keystrokes per task(KPT))

<br />
<br />


## Create a Use Case

Create a use case so that you can identify a document or set of documents that must be processed together in Document Intelligence. For example, invoices or drivier's licenses.

1. Click on the **Use Cases tab** and then click **New use case**
2. **Define a new use case**

<br />
<img width="1912" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/9f5a2f37-7b31-424d-a41e-1e7792860dce">
<br />
<br />


<br />
Choose a name that reflects the purpose of the document processing workflow you want to improve and select a table to store the document processing results for this use case:

- **Name:** Visitor Access IDs

- **Location for the extracted data:** visitors (x_snc_visitoracc_0_visitors)

<img width="799" alt="image" src="https://github.com/user-attachments/assets/1f36b6b8-8743-4883-9c5d-fb71245bd487">

<br />
<br />

<br />

3. Click **Save** and then open the use case you just created: Visitor Access IDs
<br />
<br />


<img width="1913" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/01f28db7-91d2-4ab6-b85f-d9de324dc188">

<br />
<br />


## Create Fields

 Document Intelligence uses fields to identify and extract data from documents. In this section, we will identify which fields should be extracted from our document for this Use Case.
 <br />
 <br />

1. Once you've opened the Use Case, **click on Define your fields** at the bottom of the page

<br />

<img width="1918" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/ff0887a1-eb74-4762-8520-e517b318b836">
 <br />
 <br />


2. Select Single Field

   
<br />
<br />


<img width="600" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/faaec75c-78c9-4d1f-aec1-5fe761386327">
<br />
<br />



3. Identify which fields should be extracted from our Visitor's IDs and map to the target fields in the table that we've selected for this use case:
   - **Field Name:** First Name
   - **Target Table:** visitors (pre-selected)
   - **Type:** Text
   - **Target Field:** visitor firstname (visitor_firstname)
   - **Required:** Keep Checked
   - **Create More Single Fields:** Select this toggle since we are entering multiple fields - it will keep the field screen open after we save.
   - **Click Save**



<br />
<br />

4. Repeat the same steps to create fields for:

   - **Field Name:** Last Name
     - **Target Field**: visitor lastname (visitor_lastname)

   - **Field Name:** DOB
     - **Target Field:** visitor dob (visitor_dob)

<br />
<br />
5. Review the Fields tab to ensure all of the columns are correct:
<br />
<br />

<img width="1916" alt="image" src="https://github.com/user-attachments/assets/5d6f0918-5c5a-4a07-bd16-3d0896199fad">

<br />
<br />


## Configure Data Extraction Modes

The extraction modes determine how the data is extracted in the document task. The mode changes the behavior of the fields in the Document Intelligence workspace. 

<br />

There are three types of extraction modes:

<br />

<img width="1528" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/4b813a5e-f162-400f-aa63-41d63ac5e020">

<br />
<br />
<br />

1. In the top right, select the Gear icon to open the Automation Settings:

<br />

<img width="1917" alt="image" src="https://github.com/user-attachments/assets/0ed88baa-556e-43f6-a1d0-22f9ef15b63f">

<br />
<br />
<br />

2. By default, the Recommendation extraction mode is turned on. **Toggle on:**
   - Auto-fill mode with 60% for both thresholds
      - Auto-fill mode will populate the fields as long as Doc Intel has a confidence rate of 60% or higher that the extracted information is correct and will still require an Agent's review.
   - Fully Automated mode with 90% threshold
      - Fully Automated mode will populate the fields and skip the Agent's review as long as Doc Intel has a confidence rate of 90% or higher that the extracted information is correct.


<br />

<img width="800" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/9ca43fa4-f057-4da9-b73d-a0802df379b7">

<br />
<br />


3. Click **Save**

<br />
<br />


## Creating Document Tasks
<br />
Now that we have Document Intelligence configured for our use case, we can create document tasks to review how AI detected the fields that we've defined.

<br />
<br />

1. **Select the Document Tasks tab** at the bottom of the Use Case page

<br />

2. **Create a document task**

<br />
<br />

<img width="1918" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/019ee8a2-c97f-42f1-9718-523d2f136a58">

<br />
<br />


3. **Name the document task:** Visitor Test 1
    
<br />

4. **Add the Attachment:** Upload the Driver's License provided with this lab

<br />
<br />

<img width="807" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/9d6aa690-c957-4f20-8b79-9ed8c09ddb3b">

<br />
<br />

5. Click **Add Extraction**
    
<br />

6. The Document tasks tab will display the task you just created.

<br />

7. Document Intelligence will take a minute or two to process the task
   - **Click on the refresh button** until the "Is Processed" column displays "true"
     - If the value is "false", Doc Intel is still processing the task.

<br />

8. Once the value is "true", open the Visitor Test 1 task

<br />
<br />

<img width="1916" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/78e22982-bb66-4137-84b5-cc2cf24996d4">

<br />
<br />

9. **Open in Document Intelligence** to see how AI detected the fields

<br />
<br />

<img width="804" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/39b143f7-2938-40ee-b28f-02a94362b45c">

<br />
<br />

The Document Intelligence view opens in a new tab and displays the uploaded document and the fields defined. Since this is the first document for this use case, the confidence thresholds have not been met for Auto-fill or Fully Automated processing.

<br />

Agents will manually review documents and train AI until the indicated confidence score thresholds are met.

<br />

10. **Review the extracted fields & help train AI:**

 - **Select the DOB Field** on the right pane
 - **Start typing the DOB** as it appears on the DL
 - **Hover your mouse over the correct DOB**
    - The % displayed is the confidence score
 - **Doc Intel will display a purple box on the document** to indicate where that field is extracted from.
 - **Select the correct value** to train AI

- **Repeat these steps for the other extracted values** (First Name & Last Name)

- Click **Submit**

<img width="1909" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/dbfe7fa1-f4c9-47fb-8fa9-1035cc898442">

<br />
<br /> 

11. **Navigate back** to your instance

<br />

12. **Create 3 more Document Tasks & upload the DL**
    - Once processed, open the tasks in the Document Intelligence view
    - Repeat the steps above to train AI by selecting the correct values and notice the confidence score each time
      - Note: In this lab, we are only creating a few tasks to train AI. Best practice would be to train using a minimum of 10 document tasks, with attachments, for each use case before going live.

<br />

As Doc Intel continues to process documents in this use case, the confidence score will rise and eventually auto-fill/fully automated extraction will be achieved.

<br />
<br />


## Integrations

<br />

Now that our use case is configured and we've helped train AI to build the confidence score, we are ready to integrate Doc Intel into a workflow.

<br />

There are two types of integrations to choose from:
<br />
   - The **Process Task** type: creates an integration point to automatically create and process DocIntel document tasks based on specific triggers happening in the target table.
   - The **Extract Values** type: creates an integration point to automatically propagate the extracted values to the target table when extraction has been completed in DocIntel (that is, when the document task status changes to Done).

<br />

1. **Click on the Integrations tab** at the bottom of the Use Case workspace
2. **Click Set up your first integration**

<br />
<br />

<img width="1917" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/cef92231-2675-4663-a4f8-4e375a16fbd3">

<br />
<br />

3. **Name your Integration:** Visitor ID Extraction
4. **Select the type of Integration:** Process Task
   - Acme's current 'Visitor Access' process is to receive visitor information via email - As part of the process improvement, we have added a catalog item to request Visitor Access, which will be the trigger for Doc Intel to process.
5. **Conditions:** can be left blank
6. **Create Flow:** Select Checkbox
7. **Save**

<br />
<br />

<img width="808" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/5e7befd5-4644-4726-a8fa-5a62f80aacc0">

<br />
<br />

8. In the Integrations tab, **click on the Flow** that we just created to open in Flow Designer

<br />
<br />

<img width="1917" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/4752337b-2a00-4612-8432-4d0c175530c3">

<br />
<br />


9. **Define the Trigger** for the workflow:
    - Trigger: Created
    - Table: visitors [x_snc_visitoracc_0_visitors]

<br />
<br />

<img width="1076" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/851f6f8f-c4f2-449c-b184-d97f7d0a1f7d">


<br />
<br />


10. **Define the Actions**
    - 
