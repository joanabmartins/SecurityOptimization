# SecurityOptimization

As your azure environment increases, security optimization should become a crucial and integrated part of day-to-day operations. Securing cloud infrastructure at scale requires deep insight into your optimization potential and changes to your culture to implement sustainable security improvements.

Here we provide different scripts to help you optimize you security posture on Azure. 
After clicking the button bellow you can choose what you want to deploy and fill in the parameters. 


[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjoanabmartins%2FSecurityOptimization%2Fmaster%2Fazuredeploy.json)

 <br/>
 
 * **Enable Security Center Standard** 
 All Azure subscriptions come with Security Center free enabled, but Security Center Standard helps you find and fix security vulnerabilities, apply access and application controls to block malicious activity, detect threats using analytics and intelligence, and respond quickly when under attack. You can try Security Center Standard at no cost for 30 days when you enable it. You can consult the prices that you pay after it [here](https://azure.microsoft.com/en-us/pricing/details/security-center/).
 By selecting to enable security center standard through our template we will also select the option to **automatically provision Microsoft Monitoring Agents to your machines**. 
 If you already have ASC but you want to enable the autoprovisiong of agent, you can go ahead select yes under "Deploy Security Center Standard" and write down the name for the new or existing log analytics workspace that you want the logs to be sent to.
 
  * **Enable Sentinel** 
  Microsoft Azure Sentinel is a scalable, cloud-native, security information event management (SIEM) and security orchestration automated response (SOAR) solution. By selecting **Yes** to the deployment of Sentinel we will enable Sentinel on the log analytics template and deploy a logic app that you can use in the future to receive alerts from Sentinel. 
 
 * **Assign policies to collect diagnostic logs**
 Improving security comes hand in hand with governance. You can remediate the security recommendations as they appear, but as your environment grows, it is probable that you will get that recommendation again. We propose that you solve this through governance, by making sure that some security requirements are automatically applied as you develop your environment. We suggest assigning policies to **automatically enable diagnostic logs collection from key vault, app gw, nsg, and azure firewall**. These logs will be collected in the log analytics workspace that you indicate (the template will create a new one or use one that already exists). You will automatically be able to see dashboards on those logs if you deploy our workbook.
 
 
 * **Deploy workbook to help you follow and analyze your security center recommendations, alerts and trends**
 We developed this workbook to make it easier for you to check Security Center, Sentinel and dashboards related to some of the diagnostic logs that you have enabled in one place.

 <p align="center">
  <img src="./media/workbook.PNG" width="500" alt="">
</p>


 * **What needs to be configured manually** 

->[Common Windows security logs collection in Azure Security Center](https://docs.microsoft.com/en-us/azure/security-center/security-center-enable-data-collection#data-collection-tier)

->[Continuous export of ASC recommendation and alerts](https://docs.microsoft.com/en-us/azure/security-center/continuous-export)

->[Create a run as account in automation account](https://docs.microsoft.com/en-us/azure/automation/manage-runas-account#create-a-run-as-account-in-azure-portal)

->[Connect data soureces to Azure Sentinel](https://docs.microsoft.com/en-us/azure/sentinel/quickstart-onboard#connect-data-sources)


 
 <br/>
 <br/>
 <br/>
 <br/>
 <br/>
 
 
>  FastTrack for Azure are “Professional Services” subject to the “Professional Services Terms” in the Online Services Terms and Online Services Data Protection Addendum. This document is provided “AS-IS,” WITHOUT WARRANTY OF ANY KIND. Microsoft disclaims all express, implied or statutory warranties, including warranties of quality, title, non-infringement, merchantability and fitness for a particular purpose. 
