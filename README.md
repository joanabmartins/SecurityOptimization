# SecurityOptimization

As companies increase their cloud investments, security optimization should become a crucial and integrated part of day-to-day operations. Securing cloud infrastructure at scale requires deep insight into your optimization potential and changes to your culture to implement sustainable security improvements.

Here we provide different scripts to help you optimize you security posture on Azure. 
After clicking the button bellow you can choose what you want to deploy and fill out the parameters. 


[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjoanabmartins%2FSecurityOptimization%2Fmaster%2Fazuredeploy.json)

We explain the different deployment options bellow 

 * **Enable Security Center Standard** 
All Azure subscription come with Security Center free enabled. This already gives you a big insight over you Azure environment security posture. You can see your secure score and our security recommendations. However, for production environment we definatelly advise you to enalbe security center standard.  Center Standard helps you find and fix security vulnerabilities, apply access and application controls to block malicious activity, detect threats using analytics and intelligence, and respond quickly when under attack. You can try Security Center Standard at no cost for 30 days when you enable it. You can consult the prices that you pay after it here.
 
By selecting to enable security center standard through our template we will also select the option to automatically prevision Microsoft Monitoring Agents to your machines. This way all your Azure machines will get MMA and will send security logs to a log analytics workspace, which will then be queried by ASC. That is why we ask you to also write down the name for the log analytics workspace. 
If you already have ASC but you want to enable the autoprovisiong of agent, you can go ahead select yes under "Deploy Security Center Standard" and write down the name for the new or existing log analytics workspace that you want the logs to be sent to.
 
 
 * **Assign policies to collect diagnostic logs**
 
 * **Deploy workbook to help you follow and analyze your security center recommendations, alerts and trends**
