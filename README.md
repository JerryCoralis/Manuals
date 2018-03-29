## PDF 
Motivation: creating indices for pdf textbooks. As well as ripping index metadata from PDFs.

# Creating indicies via ghostscript
1. make a .info file that contains the indices in the format specified in **.macm201_main_index.info**
2. in terminal, ensure the current directory has the index file (.info) and target PDF file is also there.
3. in terminal type: `gs -sDevice=dfwrite =q =dBATCH -sOutputFile=newfile_indexed.pdf index.info -f targetpdf.pdf`
4. bashscript **.pdfIndex.sh** takes input1=indexFile input2=targetPDF

# Extracting indices from a PDF
1. `pdftk targetExtract.pdf dump_data output index.txt`

# Import indices to a PDF
1. `pdftk targetPDF.pdf update_info index.txt output updated.pdf`
