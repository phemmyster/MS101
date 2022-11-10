# Learning Path 10 - Lab 8 - Exercise 5 - Manage and Monitor a Device in Intune

Holly Dickson wants to make managing devices easier, so she has decided to implement Microsoft Intune device categories in her pilot project. Implementing device categories will enable her to automatically add devices to groups based on categories that she defines.

As part of managing devices in Intune, Holly will create dynamic groups in the Microsoft Endpoint Manager admin center, based on the device category and device category name. After you configure device groups, users who enroll their device will be presented with a list of the categories you configured. After they choose a category and finish enrollment, their device is added to the Active Directory security group that corresponds with the category they chose.

### Task 1: Create device categories

In this task, you're going to create two device categories, one for mobile devices and the other for desktop systems. These categories will then be assigned to devices in the next task.

1. In the LON-CL1 VM, you should still be logged in as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In your Edge browser, the **Microsoft Endpoint Manager admin center** should still be open. In the left-hand navigation pane, select **Devices**. 

3. In the **Devices | Overview** window, scroll down towards the bottom of the middle pane and under the **Other** section, select **Device categories.**

4. In the **Devices | Device categories** window, select **+Create device category**.

5. On the **Create device category** window, the top of the page shows the 3 tabs involved in creating a device category. In the **1 - Basics** tab, enter **Mobile Device** in the **Name** field and then select **Next**.

6. On the **2 - Scope tags** tab, you will not define any scope tags, so select **Next**. 

7. On the **3 - Review + create** tab, select **Create**.

8. Repeat steps 4-7 to create a second device category that's titled **Desktop**.

9. Leave all browser tabs open for the next task.

### Task 2: Manage the enrolled devices

In this task, you're going to manage the Category property of the two devices that are joined to Azure AD and enrolled in Microsoft Intune. You will also review the properties and discovered apps on each device.

1. In the LON-CL1 VM, you should still be logged in as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In your Edge browser, the **Microsoft Endpoint Manager admin center** should still be open and it should be displaying the **Devices | Device categories** window after having completed the prior task.

3. In the **Devices | Device categories** window, scroll to the top of the middle pane and select **All devices**.

4. On the **Devices | All devices** window, select **LON-CL1**, which is the device that Holly joined to Azure AD, and which was automatically enrolled to Intune.

5. On the **LON-CL1** window, review the device details. Also review the actions available on the menu bar at the top of the page; these are the actions that you can perform against the device.

6. On the **LON-CL1** window, in the middle pane under the **Manage** section, select **Properties**. 

7. In the **LON-CL1 | Properties** window, note the current value of the **Device category** field is **Unassigned**. Select the drop-down arrow for this field and in the menu, note the appearance of the two device categories (Mobile Device and Desktop) that you created in the prior task. Select **Desktop**, and then on the menu bar at the top of the page, select **Save**.<br/>

    **Note:** For Android or iOS devices, you must select the **Device category** during enrollment.

8. In the **LON-CL1 | Properties** window, in the middle pane under the **Monitor** section, select **Hardware.**

9. In the **LON-CL1 | Hardware** window, review the hardware information that synced from the device. Then scroll down and review the **Conditional access** section at the bottom of the page.

10. In the middle pane under the **Monitor** section, select **Discovered apps** and review the list of apps that were discovered on the device.

11. In the **LON-CL1 | Discovered apps** window, note the navigation thread at the top of the windows (**Dashboard > Devices | All devices > LON-CL1**). Select **Devices | All devices** in this thread. This returns you to the **Devices | All devices** window.

12. Repeat steps 4-10, but this time select **LON-CL2**, which is the device that Joni Sherman joined to Azure AD in an earlier lab. Change the **Device category** value to **Mobile Device**.

13. Leave all browser tabs open for the next task.


### Task 3: Create dynamic groups for the device categories

1. In your Edge browser, the **Microsoft Endpoint Manager admin center** should still be open. In the left-hand navigation pane, select **Groups**. 

2. In the **Groups** window, select **New group** on the menu bar.

3. In the **New Group** window, enter the following information:

    - Group type: **Security**
    - Group name: **Mobile Devices**
    - Membership type: **Dynamic Device**

4. Under the **Dynamic device members** section, select **Add dynamic query**.

5. On the **Dynamic membership rules** window, the **Configure Rules** tab is displayed by default. As you can see, no rules have bee defined. Hover your mouse over the **<Choose a Property>** field to display the rule fields, and then enter the following values:

    - Property:   **deviceCategory**
    - Operator: **Equals**
    - Value: enter **Mobile Device** (Note: This must match the spelling of the corresponding category that you created, which in this case is Mobile Device)

6. Select in the **Rule syntax** field and the query syntax will appear.

7. Select **Save** on the menu bar at the top of the page.

8. On the **New Group** window, select the **Create** button at the bottom of the page. The **Mobile Devices** group should now appear in the list of groups. If it doesn't appear, select **Refresh** on the menu bar at the top of the page. 

9. Repeat steps 2-8 to create a group for desktop devices. The **Group Name** should be set to **Desktop Devices**, and in the **Dynamic membership rules** window, enter **Desktop** in the **Value** field.

10. In the **Groups | All groups** window, both new groups should appear at the top of the group list. If the **Desktop devices** group does not appear, select **Refresh** on the menu bar.

11. Leave all browser tabs open for the next task.


### Task 4: Create a conditional access policy

The modern security perimeter now extends beyond an organization's network to include user and device identity. Organizations can utilize these identity signals as part of their access control decisions.

Conditional Access is the tool used by Azure Active Directory to bring signals together, to make decisions, and enforce organizational policies. Conditional Access is at the heart of the new identity-driven control plane.

In this task, you will create a conditional access policy that Holly plans to implement in her pilot project. 

1. In your Edge browser, the **Microsoft Endpoint Manager admin center** should still be open. In the left-hand navigation pane, select **Endpoint Security**. 

2. In the **Endpoint security | Overview** window, in the middle pane under the **Manage** section, select **Conditional access**.

3. In the **Conditional Access | Policies** window, select **+New policy** on the menu bar.

4. On the **New** pane, enter the following information:  <br/>

   - In the **Name** field, enter **Conditional1**.
   - Under the **Assignments** section, select **0 users or workload identities selected**. Enter the following information in the settings that appear:
      - Under the **What does this policy apply to?**, select **Users and groups**. 
      - Under the **Include** tab, select the **All users** option.
   - Under the **Cloud apps or actions** section, select **No cloud apps, actions, or authentication contexts selected**. Enter the following information in the settings that appear:
      - Under the **Select what this policy applies to**, select **Cloud apps**. 
      - Under the **Include** tab, select **Select apps**.
      - In the **Select** pane that appears, enter **Exchange** in the Search field. In the list of search results, select the check box for **Office 365 Exchange Online**, and then select the **Select** button at the bottom of the pane.
   - Under the **Conditions** section, select **0 conditions selected**. Enter the following information in the settings that appear:
      - Under the **Device platforms** section, select **Not configured**.
      - In the **Device platforms** pane that appears, in the **Configure** field, select **Yes**. 
      - Under the **Include** tab, select the **Select device platforms** option and then select the **Windows** check box. Select **Done**.
   - Under **Access Controls**, in the **Grant** section, select **0 controls selected**. In the **Grant** pane that appears, select the **Require device to be marked as compliant** check box, and then select the **Select** button.
   - Under **Access Controls**, in the **Session** section, select **0 controls selected**. In the **Session** pane that appears, review the description of the pane but do not select any option. Select the **X** in upper right corner to close the pane.

5. On the **New** pane, select the **Create** button at the bottom of the pane. The **Conditional1** policy now appears in the policy list.

6. You created a conditional access policy to become familiar with the available options. However, the policy is not effective because you didn't enable it. To enable the policy, select the **Conditional1** policy in the policy list.  

7. In the **Conditional1** pane, the **Enable policy** setting appears at the bottom of the pane. By default, it's set to **Report-only**. Select **On** and then select **Save**. <br/>

   **Note:** You could have enabled the policy when you were in the **New** pane, before you selected the **Create** button. However, we purposely had you create the policy before enabling it to reinforce the rule that a policy, by default, is in Report-only mode and must be enabled to become effective.

You have now created a conditional access policy and enabled it for Adatum's pilot project.


# End of Lab 8
