# Learning Path 6 - Lab 6 - Exercise 1 - Implement Sensitivity labels with Azure Information Protection Unified Labels client

In your role as Holly Dickson, Adatum’s Enterprise Administrator, you have Microsoft 365 deployed in a virtualized lab environment. As you proceed with your Microsoft 365 pilot project, your next steps are to implement Sensitivity Labels with Azure Information Protection (AIP) and Windows Information Protection (WIP) at Adatum. 

**IMPORTANT:** This lab exercise consists of four tasks. In the first task you will install the AIP Unified Labeling Client, and in the second task you will create a sensitivity label and assign it to the default sensitivity label policy. The final two tasks validate the sensitivity label and label policy. The problem with this lab is that when you create a sensitivity label and label policy, it takes up to 24 hours for the label and label policy to propagate through the system. **This means that you can perform the first two tasks, but then you must wait until the next day before you can perform the final two tasks.**  

### Task 1 – Install the Azure Information Protection Unified Labeling client

To implement Sensitivity labels as part of your pilot project at Adatum, you must first install the AIP client from the Microsoft Download Center.

1. At the end of the prior lab, you were on LON-CL2. Switch to **LON-CL1**.  <br/>

	You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**. 

2. In **Microsoft Edge**, open a new tab and enter (or copy and paste) the following URL in the address bar: **https://www.microsoft.com/en-us/download/confirmation.aspx?id=53018** <br/>

	This will start the download for the AIP Unified label client.

3. In the Microsoft download center tab, on the notification bar at the bottom of the page, you will see the **AzInfoProtection_UI.exe** file being downloaded. Once the file has finished downloading, select the **Open file** link that appears below the file name.

4. The **Microsoft Azure Information Protection** wizard will open. If the wizard does not display on the desktop, select the icon for the wizard on the taskbar to display the wizard.

5. In the wizard, on the **Install the Azure Information Protection client** page, clear (uncheck) the **Help improve Azure Information Protection by send usage statistics to Microsoft** check box and then select the **I agree** button.

6. If a **User Account Control notification** dialog box appears that asks whether the app is allowed to make changes to this device, select **Yes**.

7. Once the installation is complete, select **Close**.

8. In your Edge browser, close the **Download** tab that you opened in this task to download the Azure Information Protection client.

You have successfully installed the AIP Unified Label client on the Client 1 VM.


### Task 2 – Create a Sensitivity Label

In this exercise you will create a Sensitivity Label and add it to the default policy so that it’s valid for all users of the Adatum tenant.

1. On LON-CL1, you should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In your Edge browser, you should still have a tab open for the **Microsoft 365 admin center**. If not, open an new tab and enter the following URL: **https://admin.microsoft.com**.

3.  On the **Microsoft 365 admin center**, if necessary, select **... Show all**. Select **Compliance** under the **Admin centers** group.

4. On the **Microsoft Purview** portal, in the left-hand navigation pane, select **Information protection**. 

5. On the **Information protection** page, the **Overview** tab is displayed by default. Select the **Labels** tab. A warning message is displayed in the middle of the **Labels** tab indicating: **Your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint. You can turn on here, but note that additional configuration is required for Multi-Geo environments.** <br/>

    Select the **Turn on now** button that appears on the right side of this message. This will enable Adatum to apply the Sensitivity labels inside its Microsoft 365 environment. <br/>

    Note how the message has now changed to indicate: **You can now create sensitivity labels with privacy and access control settings for Teams, SharePoint sites, and Microsoft 365 Groups.**	

6. On the **Information protection** page, select the **+Create a label** option that appears on the menu bar in the middle of the screen, below the previous message. This initiates the **New sensitivity label** wizard.

7. In the **New sensitivity label** wizard, on the **Name and create a tooltip for your label** page, enter the following information:

	- Name: **PII**
	
	- Display name: **PII**

	- Description for users: **Documents, files, and emails with PII**

	- Description for admins: **Documents, files, and emails with PII**

	- Color for users: select one of the colors that you want to assign to your sensitivity labels

8. Select **Next**.

9. On the **Define the scope for this label** page, verify the **Items** check box is selected (select it now if necessary) and then select **Next**.

10. On the **Choose protection settings for labeled items** page, select both check boxes for **Encrypt items** and **Mark items**, and then select **Next**.

11. On the **Encryption** page, select the **Remove encryption if the file or email is encrypted** option and then select **Next**.

12. On the **Content Marking** page, set the **Content Marking** toggle switch to **On**. This displays three options that enable you to customize how you want to mark files and emails. <br/>

	Select all three check boxes. Under each setting, select **Customize text**. This opens a pane to customize that particular setting. Enter the following information in the **Customize** pane for each option (select **Save** after entering the settings for each option): <br/>

	- **Add a watermark** 
		- Watermark text: **Sensitive - Do Not Share** (Hint: after entering this value, copy it so that you can paste it in the other two text settings)
		- Font size: **25**
		- Font color: **Blue**
		- Text layout: **Diagonal**
			
	- **Add a header** 
		- Header text: **Sensitive - Do Not Share**
		- font size: **25**
		- Font color: **Red**
		- Align text: **Center**
			
	- **Add a footer**
		- Footer text: **Sensitive - Do Not Share**
		- font size: **25**
		- Font color: **Red**
		- Align text: **Center**

13. On the **Content Marking** page, select **Next**. 

14. On the **Auto-labeling for files and emails** page, set the **Auto-labeling for files and emails** toggle switch to **On**. This enables a series of options that you will update in the next steps.

15. Under **Detect content that matches these conditions**, select **+Add condition** and then select **Content contains**.

16. In the **Content contains** window, select the **Add** drop-down arrow and then select **Sensitive info types**.

17. In the **Sensitive info types** window, hover your mouse to the left of the **Name** column heading. Select the check box that appears, which automatically selects all the sensitive information types. Select **Add**, which will add all these sensitive information types to your label.

18. On the **Auto-labeling for files and emails** page, all of the sensitive information types that you selected will be displayed. Scroll to the bottom on the window and update the following settings:

	- When content matches these conditions: select **Automatically apply the Label**

	- Display this message to users when the label is applied: enter **Sensitive content has been detected and will be encrypted**.
		
19. Select **Next**.

20. On the **Define protection settings for groups and sites** page, leave both check boxes blank and select **Next**.

21. On the **Auto-labeling for schematized data assets (preview)** page, do not enable Auto-labeling for for schematized data assets (preview). Select **Next**. 

22. On the **Review your settings and finish** page, review the information you entered. If any settings need to be corrected, select the corresponding **Edit** option and make any necessary changes. When all information appears correct, select **Create label**.

23. An **Error** dialog box should appear that states the generated rule blob for the label you are attempting to create is too long. The maximum size of sensitive information type selections you can make at one time per rule is **49152**. By selecting all the sensitive information types like you did in the **Sensitive info types** window a few steps back, you have exceeded this limit. <br/>

	**NOTE: We purposely had you select all the sensitive information types so that you would receive this error.** We wanted you to experience this error so that if it happens in your production environments, you will know why you received the error and how you can correct it.  <br/>

	To correct this issue, select **OK** in the **Error** dialog box, and then on the **Review your settings and finish** page, scroll down to the **Auto-labeling for files and emails** section and select **Edit**.
	
24. This will return you to the **Choose protection settings for labeled items** page in the wizard. Select **Next** on this page, select **Next** on the **Encryption** page, and then select **Next** on the **Content Marking** page. This will take you to the **Auto-labeling for files and emails** page. 

25. On the **Auto-labeling for files and emails** page, to the right of the **Content contains** condition, select the **trash can icon**. This will remove the existing **Content contains** condition for the **PII** label that you created. <br/>

	In the remaining steps, you will add a new condition that only contains two sensitivity information types rather than all the sensitivity information types like you did originally.

26. On the **Auto-labeling for files and emails** page, under **Detect content that matches these conditions**, select **+Add condition** and then select **Content contains**.

27. In the **Content contains** window, select the **Add** drop-down arrow and then select **Sensitive info types**.

28. In the **Sensitive info types** window, in the list of sensitive information types, this time only select the **ABA routing number** and the **U.S. Social security Number (SSN)** check boxes, and then select **Add**. Back on the **Auto-labeling for files and emails** page, both of these sensitive information types will appear. Select **Next**.

29. On the **Define protection settings for groups and sites** page, leave the two check boxes blank and select **Next**.

30. On the **Auto-labeling for schematized data assets (preview)** page, do not enable Auto-labeling for database columns. Select **Next**.

31. On the **Review your settings and finish** page, select **Create label**.

32. On the **Your sensitivity label was created** page, select **Done**.

33. In the **Create auto-labeling policy** pane appears, close it now. 

34. Now it's time to publish the **PII** label. On the **Information protection** window, the **Labels** tab is displayed by default. In the list of labels, if the **PII** label does not appear, select **Refresh** on the menu bar. Once the **PII** label appears, select the check box that appears to the left of it. 

35. Select the **Publish label** option that appears in the menu bar above the list of labels. This initiates a **Create policy** wizard.

36. In the **Create policy** wizard, on the **Choose sensitivity labels to publish** page, the **PII** label is already listed, so select **Next**.

37. On the **Publish to users and groups** page, you can either select **All** users and groups, or you can select specific users and groups. Select **Choose user or group**.

38. A **Users and groups** pane appears that displays all the Adatum users and groups. Hover your mouse to the left of the **Name** column heading and select the check box that appears. This will automatically select all the check boxes. Select **Done**.

39. On the **Publish to users and groups** page, select **Next**.

40. On the **Policy settings** page, select the **Users must provide a justification to remove a label or lower its classification** check box, and then select **Next**. 

41. On the **Apply a default label to documents** page, select the **Apply this default label to documents** field. Select **PII** in the drop-down menu that appears, and then select **Next**.

42. On the **Apply a default label to emails** page, select the **Apply this default label to emails** field. Select **PII** in the drop-down menu that appears, and then select **Next**.

43. On the **Apply a default label to Power BI content** page, select the **Apply this default label to Power BI content** field. Select **PII** in the drop-down menu that appears, and then select **Next**.

44. On the **Name your policy** page, enter **PII Policy** in the **Name** field, and then enter (or copy and paste) the following description for this sensitivity label policy: **The purpose of this policy is to detect sensitive information such as ABA bank routing numbers and US social security numbers in emails and documents, and to encrypt this information when it's discovered. The user must provide an explanation for removing the classification label.** Select **Next**.

45. On the **Review and finish** page, review the information you entered. If anything needs to be corrected, select the corresponding **Edit** option and make the necessary corrections. When all information is correct, select **Submit**.

46. On the **New policy created** page, select **Done**.

**STOP!!** As mentioned at the start of this lab exercise, now that you have created a sensitivity label and assigned it to the default policy, you must wait 24 hours for the label and label policy to propagate through the system before you can perform the next two tasks in this exercise. 

**Do NOT proceed to the next task!** You can continue with the training course and perform the next series of lab exercises. However, when you reach a good break time tomorrow, you should return to this lab exercise and complete Tasks 3 and 4. In Task 3, when you get to step 14, if you do NOT see the **Sensitivity** group in the Word ribbon, then you must wait until such time that it appears. 

**IMPORTANT: The appearance of the Sensitivity group in the Word ribbon is the indicator as to whether the sensitivity label has completed its behind-the-scenes provisioning,** at which time you can complete tasks 3 and 4 of this lab exercise. 


### Task 3 – Assign your Sensitivity Label to a document

In this exercise you will use the Sensitivity label that you created in the previous task to classify a document. For this task, you will sign into Microsoft 365 as Alex Wilber, who is a regular user without any elevated privileges.

**IMPORTANT:** You should not perform this task until you have waited 24 hours since you completed the prior task. After creating the sensitivity label and label policy in task 2, it takes 24 hours for the label and label policy to propagate through the Microsoft 365 system. 

**You will know when the propagation is complete and that you can continue with this task when you get to step 14 and you see the Sensitivity label group in the Word ribbon.** If this group does not appear, then the label provisioning process has not finished. If this occurs, then wait until your next break time in class and check this again.

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. To validate the sensitivity label that you created in the prior task, you must first sign out of Microsoft 365 as Holly and sign back in as Alex Wilber. <br/>

	In your Edge browser, select the **Microsoft 365 admin center** tab, and then select the circle with Holly Dickson's HD initials in the upper right corner of the screen. In the **Holly Dickson** window, select **Sign out**.

3. Once you are signed out, close all the tabs in your Edge browser except for the **Sign out** tab.

4. In the **Sign out** tab, enter the following URL in the address bar: **https://portal.office.com/** 

5. In the **Pick an account** window, select **Use another account**.

6. In the **Sign in** window, enter **AlexW@xxxxxZZZZZZ.onmicrosoft** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**.

7. On the **Enter password** window, enter **User.pw1** and then select **Sign in**.

8. If a **Get your work done with Office 365** window appears, select the X to close it.

9. On the **Microsoft Office Home** tab, select the **Word** icon in the column of app icons on the left-side of the screen. This will override the **Microsoft Office Home** tab by opening Microsoft Word Online in this same tab. <br/>

	**Note:** In the next task, you will return back to the **Microsoft Office Home** tab by selecting the **Back** arrow at the top of this **Word** tab.

10. In the **Word** tab, select **New blank document**.

11. If a **Your privacy option** window appears, select **Close**.

12. If the Word ribbon displays icons for each feature but does not break the icons out by group, then select the down-arrow on the far right-side of the ribbon. This will switch the ribbon to the traditional ribbon style that is broken out by feature group (such as Undo, Clipboard, Font, Paragraph, Styles, and so forth).

13. In the **Word** document, type **Testing personally identifiable information (PII).**

14. Because you enabled Sensitivity labels at the start of this exercise, and assuming it's been 24 hours since you created the sensitivity label in the prior task, Word should display a **Sensitivity** group on the ribbon. <br/>

	**IMPORTANT:** If you do not see this **Sensitivity** group in the ribbon, then Microsoft 365 has not finished provisioning the sensitivity label that you created in the prior task. If this occurs, then you cannot proceed with this task. As mentioned earlier, it takes 24 hours for a new sensitivity label to be fully provisioned throughout the system. If you do not see the Sensitivity group, or if you see the group (from a prior label you created) and you select the drop-down arrow in the group and do not see your new label, then you must stop at this point and not proceed until you see the Sensitivity group and your label in the group.  <br/>

	Assuming you have waited 24 hours and the **Sensitivity** group appears in the Word ribbon, select the down arrow in the **Sensitivity** group. In the drop-down menu that appears, it should display the **PII** label that you created in the prior task. Since the **PII** label is enabled for this document, a check mark is displayed next to **PII**. <br/>
	
	In this first validation test, you are going to attempt to remove this sensitivity label from being applied to this document. If you'll recall, when you created the label policy and assigned the PII label to it, you selected the option whereby users must provide justification to remove a label or to select a lower classification label. You will now verify whether this setting is functioning properly. <br/>
	
	To remove the label from this document, select the **PII** label that appears in this drop-down menu.
	
15. In the **Justification Required** window that appears, select the **Other (explain)** option. In the **Explain why you're changing this label** field, enter **Testing what happens when a label is removed** and then select **Change**.

16. In the **Sensitivity** group in the Word ribbon, select the down arrow. In the drop-down menu that appears, note that while **PII** is displayed, it no longer has a check mark displayed next to it. This indicates the PII sensitivity label is no longer being applied to this document.  

17. To re-apply the sensitivity label to the document, select **PII** in the drop-down menu. Once again select the drop-down arrow in the **Sensitivity** group. The drop-down menu that appears should display the **PII** label, and it should display a check mark next to it that indicates it is being applied to this document.

18. In the Word document, enter **111-11-1111** below the previous line of text that you entered. This number is the same format as a U.S. Social Security Number.

19. You will now save the document. On the title bar, to the right of Word, select **Document1**.  In the drop-down menu that appears, confirm the file **Location** says **Alex Wilber>Documents**. <br/>

	In the **File Name** field, rename the file to **ProtectedDocument1** and then select outside of this file name menu (select inside the document). Note the new name assigned to the file in the title bar.

20. On the right-side of the menu bar, select the **Share** button.

21. In the **Send link** window that appears, select **Anyone with the link can edit**. In the menu that appears, select **Specific people** then select **Apply**.

22. In the **Send link** window, enter **Joni** in the **Enter a name or Email address** field. In the list of users that appears, select **Joni Sherman** and then select **Send**.

23. Close the **Link sent** window. 

You have just successfully created an AIP protected Word document that is read-only protected. The document is accessible only by its creator, Alex Wilber, and by Joni Sherman (with Read-only permission), to whom the document was shared.


### Task 4 – Verify your Sensitivity Label policy

In the prior task, you created a Word document and protected it with a Sensitivity label. The PII label policy should have inserted a watermark in the document, and it should have restricted permissions on the document. To verify whether the protection that you assigned to the document works, you will first email the document to Joni Sherman and to your own personal email address. You will then test what functionality is possible for both Joni and Alex Wilber.

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Alex Wilber**. 

2. In your Edge browser, select the **Word** tab and then select the **Back** arrow. This should display the **Microsoft Office Home** tab.  

3. In the **Microsoft Office Home** tab, select the **Outlook** icon in the column of app icons on the left-side of the screen. This opens Outlook on the web in a new tab. 

4. In **Outlook on the web**, select **New Message** in the upper left part of the screen.

5. In the right-hand pane, enter the following information in the message form:

	- To: Enter **Joni** and then select **Joni Sherman** from the user list. 

	- CC: Enter your own personal email address (do NOT enter Holly's email address; instead, enter your own personal email address)

	- Add a subject: **Protected Document Test**

	- Body of the message: enter **If you can open the protected and restricted document attached to this email, then try to change it.**

6. Select **Attach** from the menu bar at the top of the screen, and in the drop-down menu that appears, under the **Suggested attachments** group, select the **ProtectedDocument1.docx** file that you created in the prior task.

7. Once the file has been attached to the email, select the file to open it. Note the watermarks that appear in the header and footer, and in the body of the document.  After reviewing the document, select the **X** in the upper right corner of the document window to close it. 

8. Select **Send**.

9. Switch to LON-CL2. 

10. In LON-CL2, you should be logged into **Outlook on the Web** as **Lynne Robbins** from a previous lab exercise. Sign out as Lynne.

11. In your Edge browser, in the **Sign out** tab, enter the following URL in the address bar: **https://outlook.office365.com** 

12. In the **Pick an account** window, select **Use another account**.

13. In the **Sign in** window, enter **JoniS@xxxxxZZZZZZ.onmicrosoft** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**.

14. On the **Enter password** window, enter **User.pw1** and then select **Sign in**.

15. If a **Welcome** window appears, select the X to close it.

16. In Joni’s **Inbox** in **Outlook on the web**, open the email that Alex just sent her by selecting the email in the Inbox. Note the **Sensitive - Do Not Share** watermark that appears in the message (these are the header and footer watermarks that you entered in the PII label).

17. Select the attached file to open it.

18. In the **Your privacy option** dialog box that appears, select **Close**. Review the document, and note the watermarks in the header, footer, and body of the document. Close the document window. 

19. This will return you to **Outlook on the web** with the email still displayed in the right-hand pane. In the body of the email, the document appears in a tile. You want to download the document. Hover your mouse over the document tile and note the two down arrows that appear. Hover your mouse over each arrow. The first displays **Download**, while the second arrow displays **More actions**. Select the **More actions** arrow, and in the drop-down menu that appears, note that it also has a **Download** option. Since you have this menu open, select the **Download** option from here.  

20. In the notification bar that appears at the bottom of the screen, select **Save.** 

21. Once the file has finished downloading, in the notification bar, select **Open.**

22. **Microsoft Word** should open along with a **Sign in** window (it may open behind the Outlook window, in which case select the **Word** icon on the taskbar to bring it forward). 

23. Because the file is RMS protected and no AIP unified labeling client is installed on LON-CL2, you need to use the native RMS features of Word Microsoft Apps and register this installation to Joni’s account. <br/>

	‎In the **Sign in** window, enter **JoniS@xxxxxZZZZZZ.onmicrosoft.com** and then select **Next.** 

24. In the **Enter password** window, enter **User.pw1** and then select **Sign in.**

25. In the **Use this account everywhere on your device** window that appears, select **This app only** to register this Office 365 ProPlus installation to **Joni Sherman’s** Microsoft 365 account.

26. The file should open in Word, since you assigned Joni with Read-only permission. Review the three notification bars that appear above the document. 

27. Try to change the file. Word should not recognize any keystrokes, and it should display the following message above the taskbar: **This modification is not allowed because the document is open for viewing only.** <br/>  

	‎**Note:** You have just verified that the permissions assigned to the file are working properly. Joni can read the file (since she was assigned Read-only permission), but she is unable to change it (no one was assigned Edit permission).

28. Close Word.

29. You will now test what happens when you attempt to open the document that was sent to your personal email address. Use your phone or classroom PC to access your personal email address. Open the email that you (in the role of Holly) just sent to your personal email address, and then attempt to open the attached file. 

30. You should receive a messaging indicating that you are not signed into Office with an account that has permission to access the document. You can optionally sign in with an account that has permission to access the file, or request access from the **AlexW@xxxxxZZZZZZ.onmicrosoft.com** account, or Cancel out of the operation. Select **Cancel**.  <br/>

	‎Since only Joni was assigned permission to read the document, you just verified that Azure Information Protection protected the document based on the PII policy parameters that you configured.

31. Remain signed into LON-CL2 and signed into Outlook on the Web as Joni. Do not close your browser.


# End of Lab 6
