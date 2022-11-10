# Learning Path 10 - Lab 8 - Exercise 1 - Prepare for Mobile Device Management in Microsoft 365

In your role as Holly Dickson, Adatum's Enterprise Administrator, you have Microsoft 365 deployed in a virtualized lab environment for your pilot project. In this lab, you will manage user devices using Intune.

In this exercise you will verify that Adatum has installed the Enterprise Mobility + Security E5 product. You will then verify that it has been assigned to your test user accounts, and you will assign a license to yourself. You will then enable device management with Intune.

### Task 1: Verify and assign Enterprise Mobility + Security licenses

In this task you will verify that Adatum has installed the Enterprise Mobility + Security E5 product and you will check how many licenses are available. You will then verify that a license has been assigned to your test user accounts, and you will assign a license to yourself.

1. Switch to **LON-CL1**. You should still be logged in as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**. 

2. In **Microsoft Edge**, you should still have a tab open for the **Microsoft 365 admin center**; if so, select that tab now. If not, enter **https://portal.office.com**, sign in as **Holly**, select the **App launcher** icon (the square made up of 3 rows of dots) that appears above the **Home** icon in the top left corner of the screen, and then in the **Apps** pane that appears, select **Admin**; this opens the **Microsoft 365 admin center** in a new browser tab.

3. In the **Microsoft 365 admin center**, select **Billing** in the left-hand navigation pane, and then under it, select **Licenses**.

4. On the **Licenses** page, note the number of licenses that are available with your tenant and the number that have already been assigned to user accounts for each of the available licenses. In your VM lab environment, 15 **Enterprise Mobility + Security E5** licenses were assigned to your tenant, and your lab hosting provider already assigned a license to the 10 pre-existing user accounts. <br/>

   Note how the **Office 365 E5** license also has 15 available with your tenant, but in this case, 11 of the 15 have been assigned to users. Your lab hosting provider assigned a license to each of the 10 pre-existing user accounts, and when you created Holly Dickson's user account back in lab 1, you assigned her a license as well. You did not assign Holly an **Enterprise Mobility + Security E5** license. <br/>
   
   In the list of licenses, select **Enterprise Mobility + Security E5**.

5. In the **Enterprise Mobility + Security E5** page, under the list of users, verify that all 10 of the pre-existing user accounts provided by your lab hosting provider have been assigned a license. <br/>

   The one user who was not assigned an **Enterprise Mobility + Security E5** license is Adatum's Enterprise Administrator, Holly Dickson. When you created Holly's user account back in Lab 1, you were instructed at that time to only assign her an Office 365 E5 license. You will now assign her an Enterprise Mobility + Security E5 license. <br/>

    To assign Holly a license, select **+Assign licenses**, which appears in the menu bar above the list of users.

6. In the **Assign licenses to users** pane, select the **Enter a name or email address** field, and in the list of users that appears, select **Holly Dickson**. Then select the **Assign** button at the bottom of the pane.

7. Close the **You assigned a license to Holly Dickson** window.

8. Leave all browser tabs open for the next task.

You have now verified the available Enterprise Mobility + Security E5 licenses in your tenant and assigned an EMS E5 license to Holly.


### Task 2: Review MDM features in Microsoft Endpoint Manager

Devices must be managed before you can give users access to company resources or manage settings on those devices. This begins with enabling device management with Intune. With Adatum's tenant, Holly will discover that Intune has been set by default as Adatum's MDM authority. This task has you navigate through various device management features in Microsoft Endpoint Manager in order to introduce you to some of the MDM functionality that's available.

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In the **Microsoft 365 admin center**, in the left-hand navigation pane under the **Admin centers** group, select **Endpoint Manager**.

3. In the **Microsoft Endpoint Manager admin center**, select **Tenant administration** in the left-hand navigation pane.

4. On the **Tenant admin | Tenant status** page, note the **MDM authority** is set to **Microsoft Intune**.

5. In the **Microsoft Endpoint Manager admin center**, select **Devices** in the left-hand navigation pane.

6. In the **Devices | Overview** page, the **Enrollment status** tab is displayed by default. By default, Intune has been set as the MDM authority in Adatum's tenant. Note the number of **Intune enrolled devices** for each device platform. Since you haven't conducted any device management tasks yet, there is no data to show on this page. However, it's still important that you become aware of the type of data that's captured. 

7. In the middle pane under the **Policy** section, select **Compliance policies**. Even though no data is currently available, review the information on the **Compliance policies | Policies** page regarding device management. After reviewing this information, perform the following steps to examine the additional compliance policy features that can be configured: <br/>

   - On the **Compliance policies | Policies** page, in the middle pane, select **Notifications**. 
   - On the **Compliance policies | Notifications** page, select **+Create notification** on the menu bar.
   - On the **Create notification** window, under the **Basics** tab, review the settings that can be configured for a notification. Select the **X** in the upper right-hand corner of the window to close it.
   - On the **Compliance policies | Notifications** page, in the middle pane, select **Compliance policy settings**. 
   - On the **Compliance policies | Compliance policy settings** page, review the settings that control the way the compliance service treats devices.
   - Once you're done reviewing the settings, select **Devices** in the **Microsoft Endpoint Manager admin center** navigation pane.

8. On the **Devices | Overview** page, in the middle pane under the **Policy** section, select **Conditional Access**. Review the information on the **Conditional Access | Policies** page. Read the information on this page regarding conditional access. Then perform the following steps to examine additional conditional access settings:  <br/>

   - On the **Conditional Access | Policies** page, in the middle pane, select **Diagnose and solve problems**. 
   - On the **Conditional Access | Diagnose and solve problems** page, under the **Common problems** section, select the **View guidance** button under **Problems configuring location-based policies**. Review the troubleshooting guidance for this problem. Note the **Recommended steps** to resolve the problem. When you're done, select the **Previous** button.
   - Repeat the prior step for each of the remaining problems on the **Conditional Access | Diagnose and solve problems** page. When you're done, in the middle pane under the **Monitoring** section, select **Sign-in logs**.
   - On the **Conditional Access | Sign-in Logs** page, under the **User sign-ins (Interactive)** tab, note the various sign-in logs that were generated thus far. 
   - Select one of the logs. In the **Activity Details: Sign-ins** pane that appears, review the data that's tracked for that particular sign-in activity under the **Basic info** tab. 
   - In the **Activity Details: Sign-ins** pane, select the other tabs to see the data captured there. When you've finished reviewing the information tracked for this sign-in activity, close the **Activity Details: Sign-ins** pane.
   - In the middle pane under the **Monitoring** section, select **Audit logs**. Note the filters provided at the top of the page - Date, Show date as, Service, and so on.
   - Select the **Date** filter. By default, this filter option is set to **Last 24 hours**. In the **Date** filter window that appears, select **Last 7 days** and then select **Apply**. This should display all the audit logs that have been created thus far in your lab. Review the information provided in the list of audit logs. 
   - In the middle pane under the **Troubleshooting + Support** section, select **New support request**. This initiates a **New support request** wizard, which may take a minute or two to initialize and display the first page in the wizard (note the **Getting things ready** message that's displayed). This feature is used to create a support request ticket that's sent to the Microsoft Support team.
   - On the first step in the wizard (**1. Problem description**), select into each of the drop-down fields to review the various options that are available. <br/>

      **IMPORTANT:** Do NOT fill out this information or submit a support request. You may be in a classroom training environment, but you're dealing with an actual Microsoft 365 tenant. As such, submitting a support request will still send the request from your training tenant to Microsoft for processing by the Support team, which we don't want to do.

9. Once you've finished reviewing the **Conditional access | New support request** page, select **Devices** in the **Microsoft Endpoint Manager admin center** navigation pane.

10. On the **Devices | Overview** page, in the middle pane under the **Policy** section, scroll down and select **Enrollment device limit restrictions**. Review the information on the **Devices | Enrollment device limit restrictions** page. Note the fact that each user has a default limit of 5 devices they can enroll into Intune. You can change this value by performing the following steps: <br/>

   - For the **Default** priority, select **All users** under the **Name** column.
   - On the **All users** page, in the middle pane under **Manage**, select **Properties**.
   - On the **All users | Properties** page, select **Edit** that appears next to **Device limit**.
   - On the **Edit restriction** page, select the **Device limit** field and select the new limit value in the drop-down menu. For example, set the value to **3**. Then select the **Review + Save** button.
   - On the **Edit restriction** page, under the **Reivew + save** tab, note the change to the device limit. Select **Save**.

11. In the **Microsoft Endpoint Manager admin center**, select **Devices** in the left-hand navigation pane. 

12. On the **Devices | Overview** page. In the middle pane under the **Policy** section, scroll down and select **Enrollment device platform restrictions**. Review the information on the **Devices | Enrollment device platform restrictions** page. Note the tabs at the top of the page. Administrators can define version and management type restrictions for each platform type (see the tabs at the top of the page). While you won't add any restrictions at this time, perform the following steps to examine the types of restrictions that can be applied - in this case, for the **Default** restriction: <br/>

   - Select each tab - Androd restrictions, Windows restrictions, MacOS restrictions, and iOS restrictions. Note the **Default** restriction appears in each tab. Regardless of the tab you're on, select **All users** for the **Default** restriction.
   - On the **All users** page, in the middle pane under the **Manage** section, select **Properties**.
   - On the **All users | Properties** page, under the **Platform settings** section, review the current settings for each platform that applies to this **Default** restriction. Then select **Edit** that appears next to **Platform settings**.
   - On the **Edit restriction** page, note the various platform settings that you can configure. Do not modify any of the settings at this time. Once you're done reviewing the settings, select **Devices** in the **Microsoft Endpoint Manager admin center** navigation pane.

13. On the **Devices | Overview** page, in the middle pane under the **Policy** section, select **Configuration profiles**. Review the information on the **Devices | Configuration profiles** page. When configuring profiles for each platform type, Microsoft Endpoint Manager provides a variety of templates that can be used as the basis for a new template. Using preconfigured templates is the quickest and most efficient way to create a configuration profile. Perform the following steps to examine the list of templates available:  <br/>

   - On the **Devices | Configuration profiles** page, select the **+Create profile** option that appears in the menu bar at the top of the page.
   - On the **Create a profile** pane that appears, select in the **Platform** field, and then select **Windows 10 and later**. 
   - Select in the **Profile type** field. Select **Templates** from the drop-down menu.
   - Review the list of templates. 
   - Do not select a template. When you've finished reviewing the available templates, close the **Create a profile** pane.   
   - If a dialog box appears at the top of the page indicating your unsaved edits will be discarded, select **OK**.  

14. Select **Devices** in the **Microsoft Endpoint Manager admin center** navigation pane.

15. In your Edge browser, leave all the tabs open for the next lab exercise. 

You have now verified that Intune is the default MDM solution for your tenant, and you have reviewed a number of the device settings that can be configured.


# Proceed to Lab 8 - Exercise 2
