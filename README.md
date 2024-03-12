# barcode-Manager
Barcode Manager Program

There is a GUI that allows you to decide if you want to start a fresh scanning sheet or work off of an old one.

Then from the GUI you can start scanning.

Once the file is created there is a sheet mangamnet window. Here you can decide to remove records from the sheet, or you can start scanning again in order to append more records to the sheet.

The purpose of this program is to allow for easy documentation of the items scanned into each box for item shipments. First a box is scanned, then each item following will be associated with said box. Until another box is scanned, then each item following with be associated with said box.

Now to end the scanning you need to input '/' which will end the scanning.

menu.py: the driver program for the GUI.

barcode.py: the driver program for the barcode scanning loop (keylogger).

processItems.py: run after the barcode loop is exited to process the items scanned and configure the sheet.

buildInvoice.py: will be run when the user closes the program to turn the working processed item list into the final invoice format.

invoiceToProcessed.py: converts invoice format to back to the processed format (just a light of all the items data).


need to add:
1. Check if filename exists before it is sent to the sheet menu.
4. Pull boxfilename and itemfilename from a sheet and make them configurable from the application
5. make the font size comfigurable from the application
6. make the application window resulation configurable from the application
7. make the application start from the running of a single executable
8. store a last used sheet in a file to autofill in for the use an existing sheet field to default to

3/11/2024
1. Added a global text size field which controlls the size of all text on the application. 
2. Now the sheet menu allows for scrolling so you can always see all the elements pulled from the working sheet.
3. Clean up working files after the invoice is generated
4. Changed the source sheet to fit the required specifications

3/10/2024
1. invoiceToProcessed.py was created with the invoiceToProcessed() function to turn the invoice sheet into the processed sheet so it can be input by the user and converted to where the program can manipulate it.
2. Now invoice files can be input so the processessing files are no longer needed by the user.

3/8/2024
1. Finished the labeling for the generateInvoice() function.
2. Made the invoice closer to human readable. (Colors and proper formatting)
3. Now the invoice file is opened at the end of the user session.
4. Now the building of the invoice is run at the end of each user session from the working processed file. Where the menu calls the invoice generation function when the user presses the quit button.

3/7/2024
1. Cleaned up the build invoice command.
2. Now the invoice command fully labels the data, inserts the data, and fills in the item instance-box number association matrix.
3. raises the size of each cell in the sheet to show the full data in the cell for a better user experience.

3/6/2024
1. Started working on the buildInvoice functionality of the program (buildInvoice.py)
2. Now the basic information required for the invoice is parsed and passed to the generate invoice where the basic parts of the sheet are created, but its a work in progress.
3. now the generate invoice function is called after the processed items function is called. (which will need to be chagned to whenever the user session is completed)


2/24/2024
1. If a box is not scanned in then the items scanned without a related box will be dropped during processing.
2. Now you can from the opening menu start with an existing record file that is input by the user.
3. Now after you interact with a file and press quit the program will open the excel file.


2/23/2024
1. Finished the ability to delete items from the file from the SheetMenu Frame.
2. Created the ability to start scanning on an existing file and in the processing append the scanned data into the existing file.


2/22/2024
1. Created the GUI in order to make it more user friendly, and make all other features possible.
2. Created the menu to allow the user to select that they want to start a new sheet, and start scanning which then calls the scanning and processing functions.
3. Then I set up the basic funcationality for displaying the scanned items to the user to see if they want to modify the sheet once created.
4. Started working on giving the user the ability to delete rows in the sheet from the GUI menu. Though I wasnt able to get it fully functioning.


2/16/2024:
1. Created the basic functionality for scanning items. (reading the input from the scanner)
2. Created the ability to tell the difference form a box, item, and unregisted using data stored in the boxes sheet and the items sheet.
3. Create the ability to process the scanned items SKU and get the extra item information to display from the item sheet.
4. Store the scanned items into a sheet for later use.