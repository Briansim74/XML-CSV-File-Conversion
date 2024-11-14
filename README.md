# XML-CSV-File-Conversion
Convert files between XML to CSV / XLSX format

<br/>In this notebook, I will be demonstrating how to convert files between CSV / XLSX and XML formats. The Python notebook used is:

1. XML.ipynb

<br/>Firstly, I will be converting a multi-sheet XLSX document into a hierarchical XML file.

<br/>Attached are the relevant files:

1. XML_test_flat.xlsx
2. Output1.xml
3. Output2.xml

<br/>In the XML_test_flat.xlsx document, it is a multi-sheet document consisting of rows of financial data values in sheet 0 - "Output_Values", and the corresponding XPaths to guide each data value in sheet 1 - "Output_XML_Path". Firstly, I converted the 2 sheets into Pandas DataFrames. Next, I sorted the DataFrames in order according to their column names, as the column names have not been ordered together. Then, I converted these DataFrames into Python dictionaries from json formatted strings. I then created a recursive function create_root using the ElementTree library. The function creates a new child node for each unexplored nested XPath, or follows the existing tree for existing XPaths, and directs each value to the end node.

<br/>For Output1, each new row entry within the xlsx document is added under a new "Rpt" XPath.

<br/>For Output2, each all row entries within the xlsx document are added under the same XPath.

<br/>The XML trees are then converted into the an XML file format "Output1.xml" and "Output2.xml" respectively.

<br/>Next, I will be converting a hierarchical XML file into a multi-sheet XLSX document. There will be 2 methods that I will be converting the XML file, which will be described below.

<br/>Attached are the relevant files:

1. FX_MAS_NEWT_OTHR.xml
2. FX_MAS_NEWT_OTHR.xlsx
3. FX_MAS_NEWT_OTHR_ET.xlsx

<br/>In the FX_MAS_NEWT.OTHR.xml file, it is a hierarchical XML document consisting of nested rows of FX trading data. 

<br/>For the first method, I converted the XML file into a json format via the xmltodict library. Then, I found the XPath key that houses the relevant trade data, 'TradData'. I then created a recursive function to obtain the 'TradData' key that houses the dictionary of values of the FX data. I then created DataFrames for both the FX values and corresponding XPath addresses, then compiling the 2 DataFrames into a single XLSX file "FX_MAS_NEWT_OTHR.xlsx".

<br/>For the second method, I parsed the XML file using the XMLPullParser from the ElementTree library, then iterated through the nested XPaths via XMLPullParser's event function, which allows each XPath nested addresses and values to be parsed and entered into separate DataFrames of FX values and XPath addresses. I then similarly compiled these 2 DataFrames into a single XLSX file "FX_MAS_NEWT_OTHR_ET.xlsx".
