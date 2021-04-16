# SecurityOptimization

When you enable Security Center, you get a group os built-in policies assign to your subscription under the Security Center category. The built-in initiative is automatically assigned, regardless of whether you have Azure Defender enabled. This initiative contains only Audit policies. The templates that you find here serve to [enforce those policies](https://docs.microsoft.com/en-us/azure/governance/policy/how-to/remediate-resources#create-a-remediation-task-through-portal), rather then just audit. Through these templates we will create an initiative in your environment with [DeployIfNotExists](https://docs.microsoft.com/en-us/azure/governance/policy/concepts/effects#deployifnotexists) policies that will automatically remmediate some of the recommendations from Azure Security Center.

<br/>

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjoanabmartins%2FSecurityOptimization%2Fmaster%2Fazuredeploy.json)

 <br/>

Instead of manually remmediate the recommendations after the fact, through these *DeployIfNotExists* policies the remmediation will happen automatically, about 15 minutes after the resource gets created or updated.

There is no ‘one size fits all’ approach to security governance. The approach you eventually adopt will vary. So, we give you the option to select which policies you want to assign. When you are deploying the template, you can select *yes* or *no* according to if you want to assign a specific policy, or not.

If you change your mind after the deployment, you just need to edit the initiative assignment and change the paramenter of that policy.

The current version of the initiative has the following policies: 
| Policy |
| ------ |
| Configure machines to receive the Qualys vulnerability assessment agent |
| Enforce https access for App Services |
| Enforce secure transfer to storage account |
| Enable diagnostic logs collection from logic apps, service bus, event hub, activity logs and key vault | 
| Install Integrated vulnerability assessment solution (powered by Qualys) | 
| Enforce https access in web apps, api apps and storage accounts | 
| Deploy Advanced Data Security on SQL servers | 
| Deploy Diagnostic Settings for Logic Apps to Log Analytics workspace | 
| Deploy Diagnostic Settings for Service Bus to Log Analytics workspace | 
| Deploy Diagnostic Settings for Event Hub to Log Analytics workspace | 
| Deploy Diagnostic Settings for Key Vault to Log Analytics workspace | 


 <br/>
 <br/>
 
After you deploy the templates, if you go to the Policy Assignment Remediation Tasks you may see this issue:
 <p align="left">
  <img src="./media/PolicyAssignmentError.png" >
</p>
<br/>
<br/>

The *DeployIfNotExists* policy requires a managed identity, and through the ARM template we cannot define the right roles for the managed identity. So, you need to **edit the assignment**, without having to change anything, just to give the right roles for the managed identity to perform the remediation tasks.
 <p align="left">
  <img src="./media/PolicyAssignmentEdit.png">
</p>

<br/>
<br/>

After that he new resources that you deploy will automatically be remediated by the policies. For the existing resources, you will need to [manually create a remediation task](https://docs.microsoft.com/en-us/azure/governance/policy/how-to/remediate-resources#create-a-remediation-task-through-portal).
<br/>
<br/>
 <br/>
>  FastTrack for Azure are “Professional Services” subject to the “Professional Services Terms” in the Online Services Terms and Online Services Data Protection Addendum. This document is provided “AS-IS,” WITHOUT WARRANTY OF ANY KIND. Microsoft disclaims all express, implied or statutory warranties, including warranties of quality, title, non-infringement, merchantability and fitness for a particular purpose. 
