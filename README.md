Research Paper Summarizer Workflow
This n8n workflow automates the process of finding, summarizing, and saving research papers on a topic of your choice. It's a simple yet powerful tool for staying up-to-date with academic research without the manual effort of reading every abstract.

✨ Features
Topic-Based Search: Automatically searches the ArXiv database for papers based on a keyword or phrase you provide.

AI Summarization: Uses the Google Gemini Pro model to generate a concise summary of each paper's abstract, highlighting the main findings.

Automated File Saving: Saves each AI-generated summary as a dedicated text file in your Google Drive.

Clean Data Formatting: Extracts and cleans up key details like the paper title, authors, and URL.

🛠️ Tools & Integrations
n8n: The core workflow automation platform.

ArXiv API: A free, public API used to fetch a list of recent research papers.

Google Gemini: A powerful large language model used for summarizing the paper abstracts.

Google Drive: Used to store the final, summarized research papers as individual text files.

🚀 How It Works
This workflow follows a simple, linear process to turn a single search term into a collection of summarized documents.

Input: The workflow is triggered manually, and you provide a research topic (e.g., "quantum computing").

Data Fetching: The workflow sends a request to the ArXiv API to retrieve the latest papers related to your topic in XML format.

Data Transformation: The raw XML data is converted into a structured JSON format. A custom Code node then takes the array of papers and splits them into individual items, allowing for per-paper processing. An Edit Fields node cleans and renames the data fields to be more user-friendly (e.g., id becomes url).

AI Summarization: Each individual paper's title and abstract are sent to the Google Gemini model. Gemini then generates a concise summary, which is added to the paper's data.

File Creation: The workflow uses a Google Drive node to create a new text file for each paper. The file's name is set to the paper's title, and the content is the AI-generated summary.

📝 How to Use
To use this workflow, you'll need to set up credentials for Google Gemini and Google Drive.

Import the Workflow: Download the workflow's JSON file and import it into your n8n instance.

Configure Credentials:

Click on the Google Gemini node and add your Google Gemini API Key as a credential.

Click on the Google Drive node and follow the OAuth 2.0 process to connect your Google account.

Run the Workflow: Go to the Edit Fields (Set) node at the beginning of the workflow and change the topic value to your desired research topic. Then, click "Execute Workflow" to run the entire process.


