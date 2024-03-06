## Doc Intel Lab

## Introduction

Document Intelligence is a machine learning (ML) solution that provides assistance to quickly and accurately extract information from documents to the Now Platform® enabling you to quickly process highly variable documents that change over time.

Many organizations today use simple optical character recognition (OCR) solutions to extract data from documents that requires significant manual configuration, and also often requires manual changes as the documents evolve. Document Intelligence extends beyond the simple OCR by using ML to identify, understand, and extract text and data from documents. This enables you to accurately automate document processing and accurately extract information from documents, even when the documents have varied text, data, and templates.

We added this capability on the platform so the data extraction from documents can easily be done but also for our customer to be able to do this from within their own Workflows on the platform. A lot of processes still involve digital documents, this can be a useful capability as organisation are progressing on their hyperautomation journey.

## Goal

In this lab, we will configure Doc Intel to automate the extraction of data from a physical form of identification (Driver's License, Government Issued ID, Passport, etc.) in order to drive efficiency.

## Use Case

ACME Inc. has a mandate to automate as much as possible within their organization to drive efficiency, reduce costs, and improve user experience. They have identified their current 'Visitor Access' process as highly repetitive and time consuming for their agents. In the current process, agents receive the visitor information via email and manually enter the required fields, into the Badging Application, in order for a vistor's badge to be printed.

As a member of ACME Inc.'s Automation Center of Excellence, you have been contacted to automate the task of a collecting visitor information, from their driver’s license or other form of physical identification, in order to streamline the process and reduce manual efforts.

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

## Create a use case

Create a use case so that you can identify a document or set of documents that must be processed together in Document Intelligence. For example, invoices or drivier's licenses.

1. Click on the **Use Cases tab** and then click **New use case**

<br />
<img width="1912" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/9f5a2f37-7b31-424d-a41e-1e7792860dce">
<br />
<br />

2. **Define a new use case**
<br />
Choose a name that reflects the purpose of the document processing workflow you want to improve and select a table to store the document processing results for this use case:

- **Name:** Visitor Access IDs

- **Location for the extracted data:** Visitor IDs

<img width="810" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/44bb3910-d1a0-4b18-95b8-3bdb77f3ad20">

<br />
<br />

<br />

3. Click **Save** and then **open the Visitor Access IDs Use Case**
<br />
<br />


<img width="1913" alt="image" src="https://github.com/vmarrone/Doc-Intel-2024/assets/151243933/01f28db7-91d2-4ab6-b85f-d9de324dc188">


