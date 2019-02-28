# Import data from MS Access #

In order to import Microsoft Access data table to MobiDB application, the following steps should be performed.

<img src="../../images/import_access/1.png" style="width:600px"/>


1.Select **External Data** tab in MS Access, then click **Export TextFile** button on the ribbon panel.

<img src="../../images/import_access/2.png" style="width:600px"/>


2.Specify the destination file name and format. By default, MS Access uses **.txt** file name extension, that should be changed to **.csv**.  Go to the next step by pressing **OK** button.

<img src="../../images/import_access/3.png" style="width:600px"/>


3.In **Export Text Wizard** check to make sure the **Delimited** option is selected ( which is set by default) and press **Advanced** button to modify the settings.

<img src="../../images/import_access/4.png" style="width:600px"/>



4.Select  comma sign (,)  as **Field Delimiter** and specify UTF-8 encoding to be used for exported data. Then press **OK** button to confirm changes.

<img src="../../images/import_access/5.png" style="width:600px"/>


5.Press **Next** to proceed.

<img src="../../images/import_access/6.png" style="width:600px"/>


6.Check to make sure **Include Field Names on First Row** option is selected. Then press **Finish** button to complete export process.

<img src="../../images/import_access/7.png" style="width:600px"/>


7.The **.csv** file is created under the file system path specified in step 2. Press **Close** button to exit.

<img src="../../images/import_access/8.png" style="width:600px"/>


8.Copy the created **.csv** file to your Android device if you want to use Mobidb for android for import.

Follow instructions written in [csv import article](csv_import.md).
