# migrated-mod-resorts

<table>
   <thead>
      <tr>
         <th colSpan="2">modresorts-1_0_war.ear</th>
      </tr>
   </thead>
  <tbody>
    <tr>
      <td>Migration plan</td>
      <td>Open Liberty on Cloud Pak for Apps on Cloud</td>
    </tr>
    <tr>
      <td>Migration complexity</td>
      <td>simple</td>
    </tr>
     <tr>
        <td colSpan="2"><b>Summary of work</b></td>
     </tr>
     <tr>
        <td>Total issues</td>
        <td>2</td>
     </tr>
     <tr>
        <td>Estimated effort (days)</td>
        <td>5.0</td>
     </tr>
     <tr>
        <td>External dependencies</td>
        <td>
          No issues found
        </td>
     </tr>
  </tbody>
</table>


### Binary project
This binary project does not contain source code and therefore does not allow you to make changes to your application before it is migrated. The application binary and application dependencies uploaded to Transformation Advisor are included here and will be used when building the Liberty based image for your application. If you provided Maven coordinates for the application binary and dependencies, they will be downloaded from the given Maven repository before building the image.
 
 ### How the bundle helps with modernization
 
  - Provides files that are necessary for containerization, accelerating the deployment to Liberty.
  
  - Provides the resources necessary to deploy your application to an OpenShift cluster using an operator.
- Tests how your application works in a container and deployed to a cluster, without neeing access to the application's source code (provided no changes are required for a successful migration).
  
  <table>
   <thead>
      <tr><th align="center" colSpan="2">Bundle contents</th></tr>
   </thead>
  <tbody>
    <tr><td colSpan="2"><b>Files for building a containerized image</b></td></tr>
    <tr><td>server.xml</td><td>Contains the Liberty server configuration for the application you are migrating. It configures application dependencies such as database connections and messaging. The server.xml may need some updates - for example, adding passwords that have been hidden by Transformation Advisor. For more details see <a href='https://www.ibm.com/support/knowledgecenter/SS5Q6W/migrationArtifacts/deployApps.html' target='_blank'>link</a>.</td></tr><tr><td>Dockerfile</td><td>This multi-stage file first downloads the application binary and dependencies (if specified), and then builds a docker image which includes your application configured in Liberty.</td></tr><tr><td>pom.xml</td><td>The pom.xml contains information about the project and configuration details used by Maven to build the project. In the case of a binary project generated by Transformation Advisor, it may contain coordinates for application binaries and dependencies.</td></tr>
    <tr>
       <td colSpan="2"><b>Files for deploying</b></td>
    </tr>
    <tr><td>Operator resources</td><td>Deploy and manage your migrated application in Cloud Pak for Applications running on OpenShift Container Platform.</td></tr>
  </tbody>
</table>  
 
 ### Documentation & support
 For more information and instructions on how to use this software see the IBM Knowledge Center [manual link](https://www.ibm.com/support/knowledgecenter/SS5Q6W/welcome.html). 

To build and deploy using Accelerator for Teams - go to the migration plan page in Transformation Advisor and select the option to use Accelerator for Teams, before downloading or pushing the bundle to Git. Accelerator for Teams was derived from the Kabanero.io software, for more details on using this feature see [Kabanero.io documentation](https://kabanero.io/docs/).

Additional information on IBM Cloud Pak for Applications can be found [here](https://www.ibm.com/support/knowledgecenter/SSCSJL/welcome.html).