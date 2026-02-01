# Presentation: Ettutu V2

**Automated Lead Generation & CRM Intelligence**

## 1\. Introduction

### The Modern Sales Challenge

In the current business landscape, sales and marketing teams face a persistent bottleneck: the "Data Gap." The internet is full of potential customers, but finding them is a manual, disjointed process. Sales representatives often spend more hours searching Google Maps, copying and pasting details into spreadsheets, and verifying email addresses than they do actually speaking to prospects. This manual friction slows down growth, burns out talent, and leads to missed opportunities.

### Enter Ettutu V2

Ettutu V2 is a purpose-built **Lead Generation & CRM platform** designed to bridge this gap. It automates the entire front end of the sales process—from discovery to outreach. By combining powerful search capabilities with AI-driven analysis, Ettutu V2 transforms the chaotic, unstructured web into a clean, organized pipeline of business opportunities.  
It acts as an automated research analyst that works 24/7. It finds businesses, visits their websites to extract contact information, reads their content to understand what they do, and organizes them into a workflow that your team can act on immediately.

### Who Is This For?

* **Sales Teams:** For Account Executives and SDRs who need a steady stream of qualified leads without the manual drudgery of research.  
* **Marketing Operations:** For growth teams running outreach campaigns who need clean, enriched data sets.  
* **Business Owners:** For leaders who need a clear view of their pipeline and lead quality without managing complex, enterprise-level software.

### Core Value Proposition

Ettutu V2 is designed to reduce the "Time-to-Lead." Instead of spending days building a list of 50 prospects, a user can generate that list in minutes—complete with emails, phone numbers, and AI-generated summaries—allowing them to focus entirely on closing deals.

## 2\. Lead Generation

The engine of Ettutu V2 is its Lead Generation module. This is not just a database of static contacts; it is an active discovery tool that builds fresh data based on your specific needs. The process flows through three distinct stages: **Discovery**, **Enrichment**, and **Analysis**.

### A. Discovery: Search Sessions

The process begins with a **Search Session**. Leveraging the Google Places API, Ettutu V2 allows users to perform hyper-targeted searches for real-world businesses.

* **Precision Filtering:** Users define exactly what they are looking for (e.g., "Web Designers," "Dental Clinics," "Accountants") and exactly where (e.g., "London, UK," "Downtown Manhattan").  
* **Radius Targeting:** You can control the scope of your search by setting a radius (e.g., 5km, 10km, 25km), allowing for both hyper-local and city-wide campaigns.  
* **Batch Processing:** The system retrieves results in organized batches. A single search session might return 20, 50, or 100 raw "Records." Each record is a verified business entity with a real address and Google rating.  
* **The "Auto-Crawl" Advantage:** For maximum efficiency, users can toggle "Auto-Crawl" before starting a search. This means that as soon as a business is found, the system automatically triggers the next stage—Enrichment—without you lifting a finger.

### B. Enrichment: Automated Crawling

Finding a business name is easy; finding the right person to talk to is hard. Ettutu V2 solves this with its automated **Crawler** system.

* **Website Discovery:** The system automatically identifies and visits the business website associated with the record.  
* **Intelligent Extraction:** The crawlers scan the website to extract vital contact data. It looks for:  
* **Email Addresses:** Parsing "Contact Us" pages and footers.  
* **Phone Numbers:** Identifying official business lines.  
* **Social Media:** Extracting links to LinkedIn, Facebook, and Twitter profiles.  
* **Crawler Modes:** Users can choose the intensity of the search:  
* *Fast Crawler:* A quick scan for immediate, obvious contact details (perfect for large lists).  
* *Deep Crawler:* Navigates multiple pages of a site to find hidden details.  
* *LLM Crawler:* Uses AI to intelligently navigate and infer contact data from complex site structures.

The **Dashboard** provides real-time visibility into this process, displaying "Data Completeness" metrics. You can see at a glance what percentage of your records have emails or phone numbers, helping you decide if you need to dig deeper.

### C. Analysis: AI-Driven Insights

Data without context is just noise. This is where Ettutu V2 differentiates itself from standard scraping tools. It employs an **AI Analyst** to qualify the leads for you.

* **Content Understanding:** The system uses Large Language Models (LLMs) to read the text on the crawled websites. It doesn't just copy the text; it "reads" it to understand the business model.  
* **Lead Scoring:** Based on the website content, the AI assigns a **Lead Quality Score** (High, Medium, Low). It can identify if a business matches your specific target profile. For example, if you are selling high-end software, the AI can flag a "High Quality" enterprise firm versus a "Low Quality" inactive blog.  
* **Smart Summaries:** The AI generates a concise **Company Description**. Instead of browsing a website for 10 minutes to figure out what a company does, your sales rep can read a two-sentence AI summary: *"This is a boutique family law firm based in Birmingham specializing in divorce and estate planning."*  
* **Industry Classification:** The system automatically tags the business with an industry focus, allowing for better segmentation later in the CRM.

## 3\. CRM Section

Once leads are generated, enriched, and analyzed, they move into the CRM (Customer Relationship Management) module. This section is designed to manage the relationship and workflow, ensuring no opportunity slips through the cracks.

### A. The Pipeline

The core of the CRM is the **Pipeline**, a visual Kanban-board interface that tracks the status of every qualified lead.

* **Visual Workflow:** Leads are represented as cards that move through customizable stages:  
* **New:** Freshly qualified leads ready for review.  
* **Contacted:** Initial outreach (email/call) has been made.  
* **Qualified:** The prospect has responded and is a good fit.  
* **Proposal:** A quote or contract has been sent.  
* **Negotiation:** Active discussions on terms.  
* **Closed:** The deal is won or lost.  
* **Drag-and-Drop:** Managing the sales flow is intuitive. Users simply drag a lead card from one column to the next, automatically updating its status and history.

### B. Records & Contact Management

Ettutu V2 maintains a clear distinction between raw data and valuable contacts.

* **Records:** These are the raw entities found during search. They remain in the database even if they aren't qualified leads yet, creating a permanent "pool" of data you can revisit.  
* **Contacts:** These are verified individuals or companies marked for safekeeping. The **Contacts View** allows you to manage your "Rolodex" separately from your active sales pipeline.  
* **Detailed Record View:** Clicking into any record provides a 360-degree view of the prospect. You can see:  
* All extracted emails and phones.  
* The AI-generated summary and score.  
* A history of tasks and interactions.  
* Google Ratings and review counts (helpful for gauging business reputation).

### C. The Chat System & Collaboration

Sales is a collaborative effort. Ettutu V2 integrates a powerful **Chat System** directly into the platform to keep communication contextual and centralized.

* **Contextual Channels:** Every Project or Lead can have its own dedicated chat channel. Team members can discuss a specific deal *within* that deal's record, rather than switching to Slack or Email.  
* **AI Assistant (Work Mode):** The chat features an integrated AI assistant. In "Work Mode," the AI has access to your data. You can ask it natural language questions like:  
* *"Show me all high-quality leads in London."*  
* *"How many records were added this week?"*  
* *"List all companies with a rating above 4.5."*  
* **General Mode:** The AI can also act as a general assistant, helping draft cold emails, generate outreach scripts, or provide advice on approaching specific industries.  
* **Real-Time Collaboration:** Powered by WebSockets, all messages and file shares appear instantly, supporting live collaboration for remote teams.

### D. Data Import & Export

Ettutu V2 is designed to be an open system that integrates with your existing tool stack.

* **Flexible Export:** You are never locked in. Users can export data at any stage.  
* **Formats:** Support for CSV (for Excel/Sheets), JSON (for developers), and Excel.  
* **Scoping:** Export your entire database, just a specific search session, or only the leads you have currently selected.  
* **CRM Integration:** The platform includes direct integration capabilities. You can push qualified leads directly to external systems like **Twenty CRM**, with planned support for Salesforce and HubSpot. This allows Ettutu to serve as the "Lead Feeder" for your main enterprise CRM.  
* **Smart Import:** You can bring your own lists into Ettutu. The **Import Wizard** allows you to upload CSV files, intelligently mapping your columns (e.g., "Company Name") to Ettutu's fields. This lets you use Ettutu's enrichment and AI scoring tools on data you already possess.

## 4\. Summary

### Operational Efficiency

Ettutu V2 is an efficiency engine. By automating the "hunt," it fundamentally changes the economics of lead generation. What used to take a team of researchers weeks can now be accomplished by a single operator in hours. The combination of **Google Places Discovery**, **Automated Crawling**, and **AI Analysis** ensures that your team is always working with high-quality, data-rich opportunities.

### Actionable Intelligence

The platform moves beyond simple data collection to provide true insight. The **Dashboard** gives leadership a high-level view of performance, active searches, and pipeline health. The **AI Analyst** ensures that sales reps aren't wasting time on irrelevant leads. The **Chat System** democratizes access to data, allowing anyone to query the database using plain English.

### Next Steps

Ettutu V2 is ready to deploy. It includes a **Demo Environment** ("Parallel Universe") that allows teams to test features safely without affecting production data. Whether you are a small agency looking for your next 10 clients or a larger operation needing to feed a hungry sales team, Ettutu V2 provides the tools to automate, analyze, and accelerate your growth.  
