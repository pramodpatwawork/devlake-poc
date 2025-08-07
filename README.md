# Apache Devlake POC (DORA matrics)

## Quick Setup Guide
Ref: https://devlake.apache.org/docs/GettingStarted/DockerComposeSetup
* I have used docker compose option for my installation.
* Download  [docker-compose.yml](https://github.com/apache/incubator-devlake/releases/download/v1.0.2/docker-compose.yml) and [env.example] (https://github.com/apache/incubator-devlake/releases/download/v1.0.2/env.example). I have downloaded version v1.0.2. you can choose any latest version. you can visit [apache devlake release url](https://github.com/apache/incubator-devlake/releases), click on version you want and download file from assests section showing in bottom of page.
* Rename env.example to .env file and put docker compose and .env file on same folder, you have to adjust docker compose yml to specify .env location if docker is not picking file. in my case .env file was not picked by docker (I was using windows docker desktop to run image) , so I specify all required variable in yml itself.
* Generate ENCRYPTION_SECRET by following instrunctions on devlake getting started guide. I was using windows so used gitash to generate keys. once key generated copy from command and define it either in .env or environment section of yml file
*  run "docker-compose up -d" command. that will download all required images (config-ui,devlake,mysql,grafana).
*  Access Config UI on url http://localhost:4000.
*  You can follow [instrunctions](https://devlake.apache.org/docs/Configuration/Tutorial) to configure github, jenkins, jira etc in ui.
*  Sequence will
   * projects> new project > enter project name and click on save.
   * Open setting click on connection, create new connection, select github, generate and enter classic token (github>profile>settings>dev setting>classic token). gihub classic token must be generated with all required permissions.
   *   Once connection created go inside project and select connection from drop-down and click next. by default all repo in your account will be shown. to locate public repository enter <owner>/repo-name then public repo will shown to selcect. For my POC I have used ```apache/incubator-devlake``` it gives me all data that I was requiring for my POC.
   *   Additionally you can define datascope config and define transformation rules in that config. I have create one with default rule.
   *   once configuration done you can click on collect data button within project and can see status.
   *   Once sync done click on dashboard link on top right corner.
   *   Go to dashboards and select github then you will be able to see bellow nice dashboard

![PRs Welcome](/images/requirements.png)
![PRs Welcome](/images/issues.png)
![PRs Welcome](/images/meanissueresolutiontime.png)
![PRs Welcome](/images/top20queuetime.png)
![PRs Welcome](/images/outstandingissues.png)
![PRs Welcome](/images/pull.png)
![PRs Welcome](/images/CICDMatrics.png)
![PRs Welcome](/images/top20contributer.png)
![PRs Welcome](/images/prmerged.png)
![CICD](/images/noofprs.png)
![CICD](/images/meantimetomergepull.png)
![CICD](/images/meantimetoclosepullinaday.png)
![CICD](/images/CICDMatrics.png)
![CICD](/images/workflow1.png)
![CICD](/images/meanworkflowrunduration.png)
