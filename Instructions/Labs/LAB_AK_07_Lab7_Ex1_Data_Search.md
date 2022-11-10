# Learning Path 7 - Lab 7 - Exercise 1 - Conduct a data search

Data subject requests (DSRs) are used to search for and extract all known information on a person of interest. A data search can come from the person in question or from an authorized source. In this exercise you will configure and export content search from the Microsoft 365 Compliance center.

**IMPORTANT:** You should only run a content search if the request is made by a Data Privacy officer or a Human Resources manager. Due to data privacy legal concerns, you should NEVER run a content search unless instructed to do so.

### Task 1 – Run a content search

Holly Dickson is Adatum’s Enterprise Administrator. In her role as the company’s Microsoft 365 Enterprise Administrator, she is responsible for implementing Adatum’s Microsoft 365 pilot project. Holly wants to use this project to test Microsoft 365 search functionality; specifically, by creating a search request for email messages sent to and from Holly and the MOD Administrator. 

**Note:** To perform this task, Holly must be assigned to the eDiscovery Manager role group so that she has the necessary permissions. You added Holly to this role group in Lab 1 at the same time that you added Joni Sherman to the role group. The reason why you were instructed to add Holly to the eDiscovery Manager role group in Lab 1 rather than at the start of this lab is that it can sometimes take up to an hour or more for permissions to successfully propagate. If you had assigned Holly to this role group just prior to this query, you would have received error messages involving parameter fields because her permissions would not have completed propagating. By adding Holly to this role group at the start of this course, enough time will have elapsed between then and now for the propagation to complete. 

1. Switch to LON-CL1, where you should still be logged in as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**. 

2. In your **Microsoft Edge** browser, select the **Microsoft 365 admin center** tab, and then in the left-hand navigation pane under the **Admin centers** group, select **Compliance**.

3. In the **Microsoft Purview** portal, select **Content search** in the left-hand navigation pane. 

4. On the **Content search** page, under the **Search** tab (which should be displayed by default), select **+New Search** in the menu bar. This initiates the **New search** wizard.

5. In the **Name and description** page, enter the following information and then select **Next**:

	- Name: **Holly Dickson test search**

	- Description: **This is a test of the content search feature to pull info on Holly Dickson and the MOD administrator**

6. In the **Locations** page, select the **Exchange mailboxes** toggle switch to turn it **On**. 

7. To the right of **Exchange mailboxes**, select **Choose users, groups, or teams**.

8. In the **Exchange mailboxes** pane that appears on the right, select the check box to the left of **Holly Dickson's** mailbox and then select **Done**.

9. In the **Locations** page, select **Next**.

10. In the **Define your search conditions** page, you want to define conditions that will search for all mail sent to and from Holly Dickson and the MOD Administrator. 
Begin by selecting **+ Add condition**. In the menu that appears, select **Sender**. Select the **Choose users** field and select **Holly Dickson** from the list of users. Select the **Choose users** field again and this time select **MOD Administrator** from the list of users.

11. Repeat the prior step to add another condition. This time select **Recipients**. In the list of users, select **Holly Dickson** and the **MOD Administrator**, just as you did in the prior step.

12. Select **Next**.

13. On the **Review your search and create it** page, review your search criteria. If anything needs to be corrected, select the appropriate **Edit** link or the **Back** button to make the correction. When everything appears correct, select **Submit**.

14. On the **New search created** window, select **Done**. This will start your search.

15. On the **Content search** window, note the **Status** of your search is **Starting**. After a minute or so, select the **Refresh** option on the menu bar. The **Status** should change to **Completed**. <br/>

	‎**Note:** Depending on how much data is accrued, a query can take some time to complete. For Adatum’s pilot project, they have not accrued much in the way of email messages, so this query that checks for email to and from Holly and the MOD Administrator should only take a minute or so to complete.

16. Once the search is complete, proceed to the next task. Leave this window open as you resume testing in the next task from this point.


### Task 2 – Export the search report

When someone opens a case to search for content, you typically export the results for further processing, oftentimes by legal teams that must investigate a case. You can also export the search report. In this task, Holly will export the search report from the previous case. In the next task, you will export the search results from the same case.

1. This task will resume from where you left off in the prior task, which was the **Search** tab on the **Content search** window. The only existing search request is the **Holly Dickson test search** that you just created and ran. <br/>

	Select the **Holly Dickson test search** record. This will open a detail pane on the right for this search request. Note the information captured for this search, including the number of items that were retrieved. Select the **Actions** button at the bottom of the pane. In the drop-down menu that appears, select **Export report**.  

2. In the **Export report** pane that appears on the right, you only want to view the items with a recognized format, so verify that under the **Output options** section, the first option is selected (**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**). <br/>

	Review the message that appears above the **Generate report** button at the bottom of the pane. Then select the **Generate report** button.

3. In the **compliance** dialog box that appears indicating a job has been created, select **OK**. This should also close the **Holly Dickson test search** pane (if not, then close it now). 

4. In the **Content search** window, the **Search** tab is currently being displayed. Select the **Export** tab.

5. In the list of Export records, select **Holly Dickson test search_ReportsOnly**. 

6. In the **Holly Dickson test search_ReportsOnly** pane that appears on the right, under the **Export key** section, select the **Copy to clipboard** option that appears below the export key. You will paste in this key in a few more steps.

7. At the top of the **Holly Dickson test search_ReportsOnly** pane, select **Download report**. In the **Open this file?** window that appears, select **Open**.

8. In the **Do you want to install this application?** dialog box that appears, select **Install** to install the **Microsoft Office 365 eDiscovery Export Tool**. 

9. Once the **eDiscovery Export Tool** is installed, an **eDiscovery Export Tool** window appears. You must paste in the export key that you just copied to the clipboard into this window. <br/>

	In the **eDiscovery Export Tool** window, select into the **Paste the export key that will be used to connect to the source** field and then press **Ctrl+V** to paste in the key. <br/>

	Then select the **Browse** button next to the **Select the location that will be used to store downloaded files** field.

10. In the **Browse For Folder** window that appears, select the **Downloads** folder and then select **OK**.

11. In the **eDiscovery Export Tool** window, select **Start** to begin the export process.

12. As soon as the **eDiscovery Export Tool** shows three green checkmarks next to the **Status** field and a **The export completed successfully** message below them, the export is done. Select the link that appears next to **Export Location**.

13. This opens a **File Explorer** window showing the **Downloads** folder. Double-click the **Results.csv** file to open Excel and view the report data for all case items found. If a **How do you want to open this file?** dialog box appears, select **Excel** if it's available. If Excel is not available, uncheck the **Always use this app to open .csv files** and then select Microsoft Edge. <br/>

	Review the spreadsheet containing the exported search report. When you're done, either close the Excel spreadsheet and the **File Explorer** window, or if you had to use Edge to view the report, close the **Results.csv** tab. 

14. You have successfully exported a case report to your local computer. Close the **eDiscovery Export Tool** window by selecting the **Close** button, and then close the **Holly Dickson test search_ReportsOnly** pane. 

15. Leave all your Edge browser tabs open for the next task.


### Task 3 – Export the search results

When someone opens a case to search for content, you typically export the results for further processing, oftentimes by legal teams that must investigate a case. While the prior task exported the search report, such a report only displays the emails and not the complete search results containing the message or document content. As such, in a real-world scenario, you could not process the report to fulfill a data subject request's legal requirements. To do so, you would need to export the seach results. In this task, you will export the search results. 
	
**Warning:** To export search results, you must be assigned the **Organization Management** role. If you're not assigned this role, you won't have the necessary permissions to export the search results. As such, this action will ultimately fail. Holly was assigned the Organization Management role back in Lab 1 in preparation for this lab.

1. This task will resume from where you left off in the prior task, which was in the **Export** tab on the **Content search** window. To export the search result, select the **Search** tab.

2. On the **Search** tab, select the **Holly Dickson test search** record. This will open a detail pane on the right for this search request. Note the information captured for this search, including the number of items that were retrieved. Select the **Actions** button at the bottom of the pane. In the drop-down menu that appears, select **Export results**. 
	
3. In the **Export result** pane that appears on the right, you only want to export the items with a recognized format, so verify that under the **Output options** section, the first option is selected (**All items, excluding ones that have unrecognized format, are encrypted, or weren't indexed for other reasons**). 

4. Under the **Export Exchange content as** section, if you had a large number of messages from multiple users, you would normally select **One PST file for each mailbox** in order to keep the messages separated by user. However, since our prior search only had a very small number of search results, it will be more efficient to have one file containing all the messages. Select **One PST file containing all messages**.

5. Review the message that appears above the **Export** button at the bottom of the pane, and then select the **Export** button.

6. In the **compliance** dialog box that appears indicating a job has been created, select **OK**. This should also close the **Holly Dickson test search** pane (if not, then close it now). 

7. In the **Content search** window, the **Search** tab is currently displayed. Select the **Export** tab.

8. In the list of Export records, select **Holly Dickson test search_Export**. 

9. In the **Holly Dickson test search_Export** pane that appears on the right, under the **Export key** section, select the **Copy to clipboard** option that appears below the export key. You will paste in this key in a few more steps.

10. At the top of the **Holly Dickson test search_ReportsOnly** pane, select **Download result**. In the **Open this file?** window that appears, select **Open**.

11. In the **eDiscovery Export Tool** window that appears, you need to paste in the export key that you just copied to the clipboard. In the **eDiscovery Export Tool** window, select into the **Paste the export key that will be used to connect to the source** field and then press **Ctrl+V** to paste in the key. <br/>

	Then select the **Browse** button next to the **Select the location that will be used to store downloaded files** field.

12. In the **Browse For Folder** window that appears, select the **Downloads** folder and then select **OK**.

13. In the **eDiscovery Export Tool** window, select **Start** to begin the export process.

14. As soon as the **eDiscovery Export Tool** shows three green checkmarks next to the **Status** field alog with a **The export completed successfully** message below them, the export is done. Select the link that appears next to **Export Location**.

15. This opens a **File Explorer** window showing the **Downloads** folder. Double-click the **Results.csv** file to open Excel and view the report data for all case items found. If a **How do you want to open this file?** dialog box appears, select **Excel** if it's available. If Excel is not available, uncheck the **Always use this app to open .csv files** and then select Microsoft Edge. <br/>

	Review the spreadsheet containing the exported search results. Note the differences between the search results in this task and the search report that you downloaded in the prior task. <br/>

	When you're done, either close the Excel spreadsheet and the **File Explorer** window, or if you had to use Edge to view the report, close the **Results.csv** tab. 

16. You have successfully exported the search results to your local computer. Close the **eDiscovery Export Tool** window by selecting the **Close** button, and then close the **Holly Dickson test search_Export** pane.

17. Leave your Edge browser and all tabs open for the next lab exercise.



# Proceed to Lab 7 - Exercise 2
