# XML-CSV-File-Conversion
Convert files between XML to CSV / XLSX format

<br/>In this notebook, there will be 3 main questions that will be addressed. For the 3 questions, I have utilised Google Colab as my IDE, and have done the programming on Colab. I have put in my thought processes for the issues that I have faced for all the questions during this project within this README file.

<br/>For Question 1, it is to use Python to convert all rows in “Output_Values” into XML format, and name it "Output.xml".

<br/>Attached are the relevant files:

1. Q1.xml
2. q1.py

For this question, I encountered a few problems on how to convert the csv into XML, while I could get the headers and labels out of the file, putting it into XML proved challenging to debug, due to the dual spreadsheet nature of the csv file. Q1.py shows the code for the conversion of csv to XML, and Output.xml shows the file that the CSV might look like potentially, if the problems are fixed without enough debugging.

<br/>For Question 2, it is to use Python to convert FX_MAS_NEWT_OTHR.xml into CSV format, and name it CSV_Output.csv.

<br/>Attached are the relevant files:

1. CSV_Output.csv
2. q2.py

I utilised Element Tree in Q2.py, which is a useful program for parsing XML data, and finding the correct ID of each data point in the XML file. However, I faced an issue whereby the data did not parse into a csv format as I had wanted to. This could be due to the outdated version of Element Tree that did not sync with Colab. With that said, I managed to convert the XML file into a CSV_Output.csv with the aid of an XML-to-CSV parser.

