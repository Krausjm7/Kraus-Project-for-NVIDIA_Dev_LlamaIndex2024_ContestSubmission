# Stock Anomaly Detection Application (v1.Beta) - NVIDIA Developer and LlamaIndex Contest 2024 Submission - Updated 11.10.2024
Stock Price Anomaly Detection Application (v1.Beta) Utilizing NVIDIA NIM Nemotron (nvidia/llama-3.1-nemotron-51b-instruct) for RAG, NVIDIA NIM Mistral (nvidia/nv-embedqa-mistral-7b-v2) for Embedding, LlamaIndex, Local Network Qdrant Vector Database, and Gradio UI in Python

My LinkedIn: https://www.linkedin.com/in/jamie-kraus-b34765106/

# Project Overview: 

This project seeks to develop an application utilizing NVIDIA models, LlamaIndex, and Qdrant Vector Database for investigating anomalies on user-selected U.S. Stocks
The Applcation will analyze US stock price data from a user-selected stock, leveraging Yahoo Finance, a machine learning algorthim, and allow users to upload relevant user-selected stock articles for RAG and inferencing.
The application will utilize an anomaly detection machine learning algorithm and the plot will be generated to show detected anomalies, peaks, and valleys.
The application will also generate an anomaly detection table where the user can study the selected stock anomaly date, close price, stock price change %, volume trading change %, and provide the stock performance % vs. S&P 500
The user can then prompt questions to the chatbox that integrates RAG powered by the NVIDIA Nemotron to conversationally understand why an anomaly occured using article PDFs as a reference to help with inferencing.

# System Engineering Architecture and Procedure

a. Please ensure you see "Conda_List_Kraus_Project" to ensure these specific library packages and their version are installed in your clean environment. \
b. A docker container must be created for the Qdrant Vector Database. Please change name within the code to your specified name. \
c. PDF Articles that I found online for the NVDA stock example are located in "NVDA Articles.zip" to test the application. \
d. Try executing code and pip install other libraries as needed for all required imports. \

# PIP Install Requirements and Versions

pip install numpy==1.26.4 \
pip install pdfplumber==0.11.4 \
pip install gradio==4.44.1 \
pip install pydantic==2.9.2 \
pip install qdrant-client==1.12.1 \
pip install requests==2.32.3 \
pip install yfinance==0.2.34 \
pip install scikit-learn==1.5.2 \
pip install matplotlib==3.9.2 \
pip install scipy==1.13.1 \
pip install pandas==2.2.3 \
pip install openai==1.54.3 \
pip install llama-index-core==0.10.58 \
pip install llama-index-embeddings-nvidia==0.1.4 \
pip install llama-index-llms-nvidia==0.1.4 \
pip install llama-index-llms-openai==0.1.31 \
pip install llama-index-readers-file==0.1.30 \
pip install torch==2.5.1 \
pip install torchaudio==2.5.1 \
pip install torchvision==0.20.1 

e. Video uploaded of me using the application "https://www.youtube.com/watch?v=qRXpffS8AxE"

Upon Execution of Code in the Gradio Interface:
1. User inputs the stock symbol.
2. Fetch stock price data (from Yahoo Finance for the selected stock over the last 3 months).
3. Application processes the stock price data to detect anomalies using an anomaly detection machine learning algorithm; plotting detected anomalies, peaks, and valleys.
4. User will then upload PDF articles of user selected stock that are published ON and 1 day before and after the detected anomalies to give a full context to the LLM for better inferencing.
5. Load PDF Documents, wait for sucessfully uploaded message. 
6. Uploaded documents will appear in the table below showing number, file directory, title, and # of pages
7. User will review the processed and plotted stock data, detected anomalies, peaks, valleys, and begin thinking of questioning to ask in the chatbox regarding the anomaly occurances
8. Use the chatbox powered by NVIDIA NIM llama-3.1-nemotron-51b-instruct prompting questions on user uploaded articles and anomaly detected dates to inference why an anomaly occured
9. Chatbox will perform RAG to obtain relevant information from user uploaded articles in the Qdrant Vector Database and include it in your prompt to make a better and contextual inference on why an anomaly occured
10. Chatbox allows for user conversational queries related to detected stock price anomalies and user uploaded and loaded PDF articles to gain insights into the stock and anomalies detected.

# FUTURE: 

Train a model for a particular stock (or an INDEX/ETF/etc) on historical stock articles and stock price, detected anomalies, peaks, and valleys from stock price history, and deploy it for this specific application. 

Integration of paid API services for stock article ethical web-scraping for a real-time generalized application. 
