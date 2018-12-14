# Description

This porject includes a set of policies to integrate Axway API Management solution with [PingIntelligence for APIs](https://www.pingidentity.com/en/platform/apiintelligence.html).
When you deploy these policies, you will be able to enable additional API protection through PingIntelligence's AI engine.

![Architecture](https://github.com/Axway-API-Management-Plus/Axway-PingIntelligence-integration-policies/images/PingIntelligene-for-APIs-Axway.png)
### Version Compatibilty
This artefact was successfully tested for the following versions:
- Axway AMPLIFY API Management 7.5.3 or 7.6.2
- PingIntelligence for APIs v.3.1.1
### Prerequisites
- Axway AMPLIFY API Management 7.5.3 or 7.6.2
- PingIntelligence for APIs v.3.1.1
# Installation
You need to use Axway Policy Studio to import provided policies:
1. Clone this project or download the *policies* folder to your machine.
2. Open Policy Studio and load your API Gateway configuration project.
3. Click the **Import Configuration Fragment** button at the top of the Policy Studio window.
4. Select **Axway-PI_integration_policies.xml** (located in the *policies* folder of this project) and click the **Open** button.
5. Accept default values by clicking **OK** in the next two windows. You should have a new container with 4 policies in it. ![Policies](https://github.com/Axway-API-Management-Plus/Axway-PingIntelligence-integration-policies/images/Policies-container.png)
6. There are 4 externalized parameters that you can find under *Environment Configuration -> Environment Settings*. ![Environment Settings](https://github.com/Axway-API-Management-Plus/Axway-PingIntelligence-integration-policies/images/env-settings.png)
7. Set *Connect to ASE Request* and *Connect to ASE Response* to an ASE server URL.
8. If you enable API key for connecting to the ASE server, specify that key in *Add HTTP Header* parameters (make sure you update two variables and Request and Response settings).
9. The last configuration step is to configure imported policies for API Manager. Click **Server Settings** in the navigation tree on the left. Expand **API Manager** in the Server Settings panel.
10. Click **Request Policies** and add the ASE Request Handler policy to the list. ![Request policy](https://github.com/Axway-API-Management-Plus/Axway-PingIntelligence-integration-policies/images/request-policy.png)
11. Click **Response Policies** and add the ASE Response Handler policy to the list.
12. Save the configuration.
13. Load the configuration to your Axway API Gateway.
14. Configure APIs in Axway API Manager.
15. For those APIs that need to be protected by *PingIntelligence for APIs*, set request policy to **ASE Request Handler** and response policy to **ASE Response Handler**.
![Request policy](https://github.com/Axway-API-Management-Plus/Axway-PingIntelligence-integration-policies/images/outbound-api-policies.png)
16. Add the following tags for each API to be protected:
	- ping_ai (required)
	- ping_cookie (optional) - if you want to analyze cookie
	- ping_login (optional) - if you want to protect a login URL
![Tags+](https://github.com/Axway-API-Management-Plus/Axway-PingIntelligence-integration-policies/images/tags.png)
17. Follow PingIntelligence for APIs documentation to register these APIs with its API Security Enforce component.
## Limitations/Caveats
- The policies are provided as a sample for integration with PingIntelligence for APIs
- Policies don't implement a possible HA configuration for PingIntelligence for APIs
## Contributing
Please read [Contributing.md](https://github.com/Axway-API-Management-Plus/Common/blob/master/Contributing.md) for details on our code of conduct, and the process for submitting pull requests to us.
## Team
[Axwaylogo]: https://github.com/Axway-API-Management/Common/blob/master/img/AxwayLogoSmall.png  "Axway logo"
## License
[Apache License 2.0](/LICENSE)


