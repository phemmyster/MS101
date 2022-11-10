# Learning Path 7 - Lab 7 - Exercise 2 - Investigate Your Microsoft 365 Data

In your role as Holly Dickson, Adatum’s Enterprise Administrator, you have Microsoft 365 deployed in a virtualized lab environment. As you proceed with your Microsoft 365 pilot project, you want to test how Adatum can investigate its Microsoft 365 data. You have decided to focus on performing a content search for deleted emails, which is a common request at Adatum, and then you want to analyze eDiscovery functionality by creating an eDiscovery case. You have asked Joni Sherman to conduct these tests on her client computer.

### Task 1 – Perform a content search for data in user mailboxes

In this exercise, you will log into Microsoft 365 on LON-CL2 as Joni Sherman, and you will perform a content search that looks for emails with the keyword **IP address**. Joni is able to access the Content Search feature in the Microsoft Purview portal because you assigned her the eDiscovery Manager role back in Lab 1. This role provides access to the Content Search feature for non-admins.

1. Switch to LON-CL2, where you should still be logged in as the local **Admin** account, and in your Edge browser, you should be logged into **Outlook on the web** as **Joni Sherman** from the prior lab dealing with sensitivity labels. 

2. Joni needs to access the **Microsoft Purview** portal. However, while she can access the Microsoft Office Home page, she does not have admin permissions; therefore, she can't access the Microsoft 365 admin center from the Microsoft Office Home page. This means that she can't access the Microsoft Purview portal from the Microsoft 365 admin center. Therefore, she will have to access the Microsoft Purview portal directly. <br/>

    To do so, select a new tab in your Edge browser and enter the following URL in the address bar: **https://compliance.microsoft.com**.

3. In the **Microsoft Purview** portal, in the left-hand navigation pane, under the **Solutions** section, select **Content search**.  <br/>

4. On the **Content search** window, the **Search** tab is displayed by default. In this tab, select **+New search** on the menu bar. This will initiate the **New search** wizard.

5. On the **Name and description** page, enter **Content Search Test** in the **Name** field and then select **Next**.

6. On the **Locations** page, verify the **Specific locations** option is selected (if necessary, select it now). Note that there are 3 groups of locations. Each group has an On/Off toggle switch, and they are all set to Off by default. If you select all locations or set all 3 toggle switches to On, the query will run for an hour or more. <br/>

    Since you do not have time in this lab to search all three locations, set the toggle switch to **On** for the **Exchange mailboxes**. Leave the other two locations turned **Off**. <br/>

    Note the **Included** setting for the **Exchange mailboxes** location is set to **All**. Therefore, all mailboxes will be searched. This could be time consuming in a real-world scenario; however, in your lab tenant, there's such a small number of mailboxes that it won't have a negative impact on search run times. <br/>

    Select **Next**.

7. On the **Define your search conditions** page, enter **IP address** into the **Enter keywords** field and then select **Next**.

8. On the **Review your search and create it** page, review your selections. If anything needs to be changed, select the appropriate **Edit** link and make the necessary changes. Otherwise, if everything is correct, select **Submit**.

9. On the **New search created** page, select **Done**.

10. On the **Content search** page, note the **Status** of the **Content Search Test** search that you just created is set to **Started**. After a minute or so, select the **Refresh** option on the menu bar. Continue to do so until the **Status** displays **Completed**. <br/>

    **Note:** It may take a couple of minutes for the query to complete. 

11. When the content search finishes, select **Content Search Test**. In the **Content Search Test** pane that appears, in the **Summary** tab, review the **Status** section to see a summary of the information that was captured. <br/>

    Then select the **Search statistics** tab. Select each of the sections and review the data that was captured.

12. Close the **Content Search Test** pane.

13. Leave the Microsoft Purview portal open and continue with the next task.

You have successfully performed a content search for a specific key word across all Exchange mailboxes in your tenant.
 

### Task 2 – Create an eDiscovery case and search for data in mailboxes on hold

In this task, you will create an eDiscovery case, add an In-Place Hold to the case to preserve mailbox content, and create a search to discover data from the hold. You will continue using Joni Sherman’s user account. Having been assigned the eDiscovery Managers role back in Lab 1, Joni has the permissions necessary to create an eDiscovery case.

1. You should still be logged into LON-CL2 as the **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Joni Sherman**. 

2. The **Microsoft Purview** portal should still be open in a tab in Microsoft Edge. If so, select that tab now. If not, then enter the following URL in the address bar: **https://compliance.microsoft.com.** 

3. You'll begin by creating an eDiscovery case for Exchange mailboxes that contain emails containing the keyword **IP Address**. <br/>

    In the **Microsoft Purview** portal, in the left-hand navigation pane, select **eDiscovery**, and then under it, select **Standard**.

4. On the **eDiscovery (Standard)** window, select the **+Create a case** option in the menu bar.

5. In the **New case** window that appears, enter **IP Address Violation** in the **Name** field and select **Save**.

6. On the **eDiscovery (Standard)** window, select **IP Address Violation** in the list of cases.

7. You'll now add an In-Place Hold to the case to preserve mailbox content. <br/>

    On the **eDiscovery (Standard) > IP Address Violation** window, the **Home** tab is displayed by default. Select the **Hold** tab.

8. Select **+Create** on the menu bar to create a new hold. This initiates the **New Hold** wizard.

9. On the **Name your hold** page, enter **IP Address Violation - Content** into the **Name** field and then select **Next**.

10. On the **Choose locations** page, set the toggle switch to **On** for the **Exchange mailboxes** location. 

11. Under the **Included** setting for the **Exchange mailboxes** location, select **Choose users, groups, or teams**.

12. On the **Exchange mailboxes** pane that appears, select the check box next to **Lynne Robbins**, and then select **Done**.

13. On the **Choose locations** window, verify the **Included** column for the **Exchange mailboxes** location displays a value of 1. Select **Next**.

14. On the **Query** page, enter **IP address** into the **Keywords** box and then select **Next**.

15. On the **Review your settings** page, review the values and select **Edit** next to any that need to be modified. When you are satisfied with the settings, select the **Submit** button.

16. When you receive a **Succeeded** message, select **Done**.

17. This returns you to the **Hold** tab on the **eDiscovery (Standard) > IP Address Violation** window. Select the **Searches** tab.

18. You'll now create a search to discover data from the mailboxes that were placed on hold (ion this case, Lynne Robbins' mailbox). Specifically, you'll search for email messages containing the keyword **IP address**.  <br/>

    On the **Searches** tab, select **+New search** on the menu bar. This initiates the **New search** wizard.

19. On the **Name and description** page, enter **IP Address Violation - Search** in the **Name** field. Select **Next**.

20. On the **Locations** page, select the **Locations on hold** option and then select **Next**.

21. On the **Define your search conditions** page, enter **IP Address** in the **Keywords** field. Select **Next**.

22. On the **Review your search and create it** page, review the values and select **Edit** next to any that need to be modified. When you are satisfied with the settings, select the **Submit** button. 

23. On the **New search created** page, select **Done**.

24. This will initiate a search query that looks for the keywords **IP Address**. 

25 On the **eDiscovery (Standard)** window, note the **Status** of **IP Address Violation - Search** is set to **Started**. After a minute or so, select the **Refresh** option on the menu bar. Continue to do so until the **Status** displays **Completed**. <br/>
 
26. When the content search finishes, select **IP Address Violation - Search**. In the **IP Address Violation - Search** pane that appears, in the **Summary** tab, review the **Status** section to see a summary of the information that was captured. <br/>

    Then select the **Search statistics** tab. Select each of the sections and review the data that was captured.

27. Close the **IP Address Violation - Search** pane.

28. Leave the Microsoft Purview portal open.

29. Leave LON-CL2 open as well as all other browser tabs and continue with the next task.


You have now created an eDiscovery case, added an In-Place Hold to preserve mailbox content, and created a search to discover data from the mailbox that was placed on hold.


# End of Lab 7
