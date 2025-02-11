---
id: 13-wisdom-integration
title: Wisdom Integration
---
import useBaseUrl from "@docusaurus/useBaseUrl";

The Amazon Connect CTI Adapter allows for integration with Amazon Connect Wisdom.

<img src={useBaseUrl('/img/shared/wisdom0.png')} />

The integration between Wisdom and the CTI Adapter first requires that Wisdom is set up in the Amazon Connect instance that the CTI Adapter is integrated with. See [here](https://docs.aws.amazon.com/connect/latest/adminguide/amazon-connect-wisdom.html) for full instructions.

Before proceeding with the below, please ensure that Wisdom articles are properly showing up in your Wisdom instance for the specific user you are testing.

**Amazon Connect Wisdom Permission Sets:**

Salesforce users accessing Amazon Connect Wisdom in Salesforce must belong to either the *AC_Wisdom* permission set, or the *AC_Administrator* permission set.

1. In *setup*, search for and select *permission sets*.
2. Select either the *AC_Wisdom* or the *AC_Administrator* permission set
3. Select *Manage Assignments*, and add all relevant users to the permission set of choice.

**Setting up Amazon Connect Wisdom in the CCP Overlay:**

1. Navigate to your CTI Adapter
2. Scroll down to the Features section and create a new feature
<img src={useBaseUrl('/img/classic/wisdomclassic0.png')} />
3. Create a new feature with the following values:
    - AC Feature Name - FEATURE_WISDOM_PANEL
    - Value - Enabled: true
<img src={useBaseUrl('/img/classic/wisdomclassic1.png')} />
4. In addition, you can also include the `IgnorePermissionSet` setting to the value of the feature on a new line. This setting will show Wisdom if it is enabled regardless of whether the
logged in user belongs to the *AC_Wisdom* or the *AC_Administrator* permission set. This setting is required if the logged in user has the `View Setup and Configuration` profile setting set to false.
    - IgnorePermissionSet: true

<img src={useBaseUrl('/img/shared/wisdom10.png')} />
5. Open the ccp, observe that there is a tab with Wisdom in the CCP Overlay.

<img src={useBaseUrl('/img/shared/wisdom0.png')} />

Wisdom can be popped out into a new window by pressing pop out button.

<img src={useBaseUrl('/img/shared/wisdom3.png')} />

**Accessing the Tabbed Version of Wisdom:**

Wisdom is also accessible in Tabbed form.

<img src={useBaseUrl('/img/classic/wisdomclassic2.png')} />
<img src={useBaseUrl('/img/classic/wisdomclassic3.png')} />

**Accessing the Component Version of Wisdom:**

The final method of accessing Wisdom in Salesforce is through the Wisdom component.

1. Navigate to Object Manager in Setup in Lightning
2. Select either Task or Case (note: the Wisdom component is embeddable in other pages as well, but you may need to write custom classes in order to do so.)
3. Select *Page Layouts*
4. Select the appropriate layout
5. Select *Visualforce Pages* in the top component
<img src={useBaseUrl('/img/shared/wisdom8.png')} />
6. Click and drag the appropriate Wisdom visualforce page into the desired location
7. Save the layout
8. Navigate to a task page
<img src={useBaseUrl('/img/classic/wisdomclassic4.png')} />

