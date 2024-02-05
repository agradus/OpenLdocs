# OpenL Tablets BRMS Demo Package Guide

## Preface

This preface is an introduction to the *OpenL Tablets Demo Package Guide*.

This guide describes a complete OpenL Tablets Demo package which contains configured and ready to demonstrate infrastructure for the OpenL Tablets product. The Demo package enables a user to develop business rules and manage business rule sets in OpenL Tablets WebStudio, and then execute these rules as web services ready to be used by solution applications.

## OpenL Tablets Demo Package

To make work with OpenL Tablets WebStudio more comfortable and quicker to start, several rule projects are already loaded in the user workspace. As a result, the user can work on projects already created from OpenL Tablets templates or, when necessary, create their own projects via Repository in OpenL Tablets WebStudio. In addition, to demonstrate usage of rules in applications, a user can also invoke rules of the preloaded project via the OpenL Tablets Rule Services Demo Client application deployed in the Demo package by default.

The Demo package is a ZIP file that can be downloaded at <https://openl-tablets.org/downloads>, **Demo** (ZIP) link. After unzipping this file, the Demo package consists of the Eclipse Jetty web server version 10.0.17, with three web applications located in the `\jetty-home-10.0.17\webapps\` folder.

**Note:** There is no need to set up `JDK`. The Demo package also works with only `JRE` installed. Note that only **Java 11** is currently supported.

These applications are as follows:

-   `webstudio`
-   `webservice`
-   `ROOT`

For Windows, to start the OpenL Tablets Demo package, locate the `<unzipped Demo package folder>\jetty-home-10.0.xx\start.cmd` file and run it by double clicking or via the console window commands. For Linux, run the `<unzipped Demo package folder>\jetty-home-10.0.xx\start` file. The browser is expected to be launched automatically; otherwise, use the following link to the **OpenL Tablets Demo welcome page**:

`http://localhost:8080/`

However, there are some specifics of launching OpenL Tablets Demo package under Linux and Mac OS. A working directory for OpenL Tablets Demo package is located at `<unzipped Demo package folder>\jetty-home-10.0.xx\openl-demo\`. After unzipping the `OpenL Tablets Demo Package` file, a user must change access rights to the `sudo chmod 775 <unzipped Demo package folder>/start` file.

For more information on deployment, see [OpenL Tablets Installation Guide > Deploying OpenL Tablets WebStudio](https://openldocs.readthedocs.io/en/latest/documentation/guides/installation_guide/#deploying-openl-tablets-webstudio).

After starting Demo, OpenL Tablets WebStudio installation wizard does not appear. OpenL Tablets WebStudio is preconfigured in a single user mode. A user sees the OpenL Tablets Demo welcome page at startup.

![](demo_guide_images/5b123378c2224806ca5621e6d6cc9e63.jpeg)

*OpenL Tablets Demo welcome page*

Use the following links to the applications available at the OpenL Tablets Demo welcome page:

|  Demo application       | URL                                            |
|-------------------------|------------------------------------------------|
|  WebStudio              | `http://localhost:8080/webstudio`              |
|  Rule Services          | `http://localhost:8080/webservice`             |
|  Rule Services Demo App | `http://localhost:8080/webservice-client.html` |

The following sections provide more details on Demo package work:

-   [OpenL Tablets WebStudio in a Demo Package](#openl-tablets-webstudio-in-a-demo-package)
-   [OpenL Tablets Rule Services in a Demo Project](#openl-tablets-rule-services-in-a-demo-project)
-   [OpenL Tablets Rule Services Demo Client in a Demo Package](#openl-tablets-rule-services-demo-client-in-a-demo-package)
-   [OpenL Tablets Demo Package as Common Deployment Pattern](#openl-tablets-demo-package-as-common-deployment-pattern)
-   [Demo Package Security Policy](#demo-package-security-policy)

### OpenL Tablets WebStudio in a Demo Package

OpenL Tablets WebStudio is preconfigured in a single user mode. A user is automatically signed in and sees the welcome start page.

The following topics are included:

-   [Rules Editor](#rules-editor)
-   [Repository Editor](#repository-editor)
-   [Administration](#administration)

#### Rules Editor

Several examples and tutorials are already in the **No Changes** status, therefore available in **Rules Editor** by default. For more information on how to manage rules in Rules Editor, see [OpenL Tablets WebStudio Guide > Using Rules Editor](https://openldocs.readthedocs.io/en/latest/documentation/guides/webstudio_user_guide/#using-rules-editor).

![](demo_guide_images/3d9e3c989ff6649c2a9c99be85d8452b.png)

*Projects in Rules Editor available for editing*

#### Repository Editor

Users can work with projects loaded in Repository in the Demo package and create their own new projects. For more information on how to manage projects in Repository, see [OpenL Tablets WebStudio Guide > Using Repository Editor](https://openldocs.readthedocs.io/en/latest/documentation/guides/webstudio_user_guide/#using-repository-editor).

The “Example 3 – Auto Policy Calculation” project is already deployed using the deploy configuration “Example 3 – Auto Policy Calculation” and can be used via OpenL Tablets Rule Services as described in [OpenL Tablets Rule Services in a Demo Project](#openl-tablets-rule-services-in-a-demo-project) in OpenL Tablets Web Services Demo Client as described in [OpenL Tablets Rule Services Demo Client in a Demo Package](#openl-tablets-rule-services-demo-client-in-a-demo-package).

As OpenL Tablets WebStudio is preconfigured in a single user mode, and all projects in Repository are created and modified by the “DEFAULT” user.

![](demo_guide_images/de34b4ee4b573302af007b841d1eb191.png)

*The whole list of rules projects in Repository of the Demo package*

#### Administration

By default, user workspace, history, and design repository are configured as local and located in the `openl-demo` folder of the `<unzipped Demo package folder>\jetty-home-10.0.xx\` directory. This setting simplifies configuration and usage of the Demo package. Note that a default directory can be changed to another one as described in [OpenL Tablets WebStudio Guide > Managing System Settings](https://openldocs.readthedocs.io/en/latest/documentation/guides/webstudio_user_guide/#managing-system-settings).

![](demo_guide_images/d4e08c04cc55071f60b74c3508b1e274.png)

*Common system settings in Administration*

Deployment Repository is set to use the Database (JDBC) connection. An appropriate URL `jdbc:h2:./openl-demo/repositories/deployment/db;AUTO_SERVER=TRUE;DB_CLOSE_DELAY=20` is configured by default and defined in the OpenL Tablets WebStudio `webstudio.properties` file in the `<unzipped Demo package folder>\jetty-home-10.0.xx\` folder.

![](demo_guide_images/e431646eb5b545f6625b9f828f1c2dcb.png)

*Settings of Design and Deployment repositories in Administration*

### OpenL Tablets Rule Services in a Demo Project

By default, a project from the “Example 3 – Auto Policy Calculation” template is deployed to Deployment Repository from OpenL Tablets WebStudio by a startup script.

To use this project as an example of project deployments as described in [OpenL Tablets Rule Services Demo Client in a Demo Package](#openl-tablets-rule-services-demo-client-in-a-demo-package), several settings are defined in Rules Configuration of the project. It is set up that only \*DriverRisk\*, \*DriverAgeType\*, \*AccidentPremium\* are wildcards, and rules are included and can be used from the OpenL Tablets Rule Services Demo Client application.

![](demo_guide_images/5f418d078e1bfd1052ae98c493d89d68.png)

*OpenL Tablets Rule Services main page and the project deployed on it*

The demo does not restrict any deployments of other projects nor has any other limitations so the users can deploy their own projects in Demo setup. If a user deploys anything else, a full list of deployed projects appears on this page including user’s projects.

**Swagger UI** is a third party tool used for testing services. For more information on Swagger UI and its usage in OpenL, see [OpenL Tablets Rule Services Usage and Customization Guide > Appendix D: OpenAPI Support](https://openldocs.readthedocs.io/en/latest/documentation/guides/rule_services_usage_and_customization_guide/#appendix-d-openapi-support).

### OpenL Tablets Rule Services Demo Client in a Demo Package

OpenL Tablets Rule Services Demo Client application is an application specially created to demonstrate usage of OpenL Tablets rules via OpenL Tablets Rule Services. OpenL Tablets Rule Services Demo Client is a simple web page that must be used to check that rules are easily accessible from other applications via web services.

**Note:**  OpenL Tablets Rule Services Demo Client invokes only several methods of a particular predeployed “Example 3 – Auto Policy Calculation” project. It means that other projects deployed by a user cannot be used from within the OpenL Tablets Rule Services Demo Client application.

OpenL Tablets Rule Services Demo Client application allows to define a driver type by age and gender, get premium per accident, or determine how risky a driver is according to business rules specified in the “Example 3 – Auto Policy Calculation” project.

![](demo_guide_images/21a9535e63bf7b98584101d6090341fa.png)

*Executing DriverAgeType rule and getting results via OpenL Tablets Rule Services Demo Client*

A user can change the values of input parameters in the fields and click the **Execute** button. The corresponding result is displayed below the list of rules to call.

In OpenL Tablets Rule Services Demo Client application, a simple HTTP client is used. It is an example of how to create a simple client with zero dependencies.

### OpenL Tablets Demo Package as Common Deployment Pattern

The easiest way to get introduced to using OpenL Tablets rules as OpenL Tablets Rule Services in the application is to explore the OpenL Tablets Demo package. This Demo configuration represents a general usage scenario of the OpenL Tablets product.

Common deployment scenario is as follows:

-   Deploy OpenL Tablets Rule Services, OpenL Tablets WebStudio, and Rules Repository, such as Database, to the web server.
-   Configure repository configurations in OpenL Tablets WebStudio, and OpenL Tablets Rule Services.

Ensure the ‘deployment’ repository is configured the same way in both applications, see configurations in Demo.

```
Release 5.27
OpenL Tablets Documentation is licensed under a Creative Commons Attribution 3.0 United States License.
```
