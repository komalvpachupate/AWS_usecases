Data Extraction fom PDF's using textract:

Information Memorandom pdf's: An information memorandum is a document prepared by your company to provide a 
	                      comprehensive overview of your business to prospective investors.

Data: PDF files 

Entities extraction: Issuer imformation extraction (Issuer name, issue date, coupons info, etc)

Approach:
1) for text extraction from pdf : Pypdf2, pdfminer, tabula for table extraction. 
   Issues - Not woking for scanned pdf
2) Pytesseract : Working for both normal and scanned pdf
   Issues - taking time to run for 40 pages pdf taking 10 to 15 min to run
 - Extracted data from above method going to NER model and regular expression 
 - Issues: Low accuracy, time consuming, 

AWS :
Services: Textract, Lambda function, s3, 
 - When object comes in s3 bucket, lambda function get triggered and cretes textact job sends notification
   second lambda function gets triggered where table from the pdf get extracted and using pandas data 
   manupulation extracting required information from pdf. 

