# Learning Path 10 - Lab 8 - Exercise 4 - Enroll a Windows device

One of Adatum’s goals for their Microsoft 365 deployment is to enroll their Windows 10 devices to Microsoft Intune so that the devices can be managed by MDM. As part of her pilot project, Holly Dickson wants to enroll the LON-CL1 PC to Intune. In this exercise, you will first verify that the device is not currently enrolled, and having done that, you will enroll the device to Azure AD and Intune and then verify the enrollment. 

During her pilot project, Holly plans to use certificates with Intune to authenticate Adatum’s users to applications and corporate resources through VPN, Wi-Fi, and email profiles. By using certificates to authenticate these connections, Adatum’s end-users won't need to enter usernames and passwords, which helps to make their access seamless. 

### Task 1: Verify the device is not enrolled

Holly must begin by verifying that the device she wants to enroll into Intune (LON-CL1) is not already enrolled. 

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In your **Edge** browser, the **Microsoft Endpoint Manager admin center** should still be open in the **Devices - Microsoft Endpoint Manager admin center** tab. Select this tab.

3. In the **Microsoft Endpoint Manager admin center**, in the left-hand navigation pane, select **Devices**.

4. In the **Devices | Overview** window, in the middle pane, select **All devices**.

5. In the **Devices | All devices** window, verify that LON-CL2 is the only device listed in the details pane. You have just verified that LON-CL1 is not enrolled into Intune. <br/>

   **Note:** LON-CL2 was enrolled into Intune in an earlier lab when you configured integration between Azure AD and Intune. When you joined LON-CL2 to Azure AD, it was automatically enrolled to Intune.  

6. You now want to start the **Certificates** MMC for LON-CL1. In the Search field on the taskbar, enter **run**, and then in the list of search results, select **Run**.

7. In the **Run** window, enter **certlm.msc** in the **Open** field and then select **OK**. If a **Do you want to allow this app to make changes to your device?** dialog box appears, select **Yes**.

8. Maximize the **certlm – [Certificates – Local Computer]** window that appears and then drag the pane divider to the right so that you can see the entirety of the left-hand pane. 

9. In the left-hand pane, select the right arrow (>) next to the **Personal** folder to expand it. Select the **Certificates** child folder under the **Personal** folder. Verify that only the localhost certificate appears. 

10. Minimize the **certlm – [Certificates – Local Computer]** window as you will use it in a later task.

### Task 2: Enroll the device to Azure AD and Intune

In this task, you want to enroll LON-CL1 to Azure AD and Intune.

1. In **LON-CL1**, enter **access work** in the Search field on the taskbar, and then in the list of search results, select the **Access work or school** system settings app.

2. In the **Settings** app, in the **Access work or school** section, select **+Connect**.

3. In the **Microsoft account** window, on the **Set up a work or school account** page, under the **Alternate actions** section, select **Join this device to Azure Active Directory**.

4. On the **Sign in** page, enter **Holly@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**.

5. On the **Enter password** page, enter **User.pw1** in the **Password** field and then select **Sign in**.

6. On the **Make sure this is your organization** dialog box, review the information and if everything looks correct, select **Join**.

7. On the **You're all set!** page, select **Done**.

8. In the **Settings** app, close the **Access work or school** page by selecting the **X** in the upper right-hand corner.

9. In your Edge browser, select the tab containing the **Microsoft Endpoint Manager admin center**. The **Devices | All devices** page should still be displayed. Currently it displays only LON-CL2. Select **Refresh** on the menu bar at the top of the detail pane. Verify that **LON-CL1** appears in the list of devices along with **LON-CL2**. <br/>

   You should also note that in the list of devices, LON-CL1 was identified as Corporate-owned device, whereas LON-CL2 was identified as a Personal device. Since LON-CL1 was enrolled by Holly, an administrator, LON-CL1 is classified as a Corporate device. Conversely, since Joni Sherman, a non-administrator, enrolled LON-CL2, device ownership is classified as a Personal device. <br/>

10. Leave all browser tabs open for the next task.

### Task 3: Verify the device is enrolled to Azure AD and Intune

In an earlier lab you configured integration between Azure AD and Intune. Because of that, any device that is joined to Azure AD is automatically enrolled to Intune. In this task you will join LON-CL2 to Azure AD, which will automatically enroll it into Intune.

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In **LON-CL1**, select the **certlm – [Certificates – Local Computer]** icon on the taskbar.

3. In the **certlm – [Certificates – Local Computer]** console, in the left-hand navigation pane, the **Personal > Certificates** folder should already be selected from the earlier task. In the menu bar, select **Action** and then select **Refresh**. In the details pane, verify that several certificates appear along with the **localhost** certificate, which was the only certificate originally in this folder.<br/>

    **Note**: These certificates were added when you joined the LON-CL1 device to Azure AD, which in turn enrolled it to Intune.

4. Close the **certlm – [Certificates – Local Computer]** window. 

5. In your **Edge** browser, select the **Azure Active Directory** tab.

6. In the **Azure Active Directory admin center**, in the left-hand navigation pane, select **Azure Active Directory**. 

7. In the **Adatum Corporation | Overview** page, in the middle pane under the **Manage** section, select **Devices**.

8. In the **Devices | Overview** page, in the middle pane, select **All devices**.

9. In the **Devices | All devices** page, both **LON-CL1** and **LON-CL2** should be displayed. Drag the horizontal scroll bar to the right until the **MDM** column is visible. Note that both devices are enrolled to **Microsoft Intune**.  <br/>

    **Note:** This view lists devices that are joined to Azure AD. Remember that you configured integration between Azure AD and Intune, and because of that, any device that is joined to Azure AD is automatically enrolled to Intune.

10. Leave all browser tabs open for the next task.


# Proceed to Lab 8 - Exercise 5
