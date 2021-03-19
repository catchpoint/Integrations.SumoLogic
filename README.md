# Catchpoint - Sumo Logic Integrations

## Introduction

Sumo Logic is a cloud-based log management and analytics service that leverages machine-generated big data to deliver real-time IT insights. In this blog post, we discuss how you can integrate Catchpoint with Sumo Logic. The integration involves pushing data from Catchpoint to Sumo Logic using Webhooks and comes with a pre-built dashboard.
Once this Integration is complete, Sumo Logic users can utilize the default dashboards or also create their dashboards.
This page provides instructions for setting up Test Data webhooks in catchpoint and HTTP source in sumo logic.

**Log Types**

Catchpoint will push a JSON-formatted test data to the subscriber using a HTTP/HTTPS Post request when enabled.  The data is pushed on each test runand sent over the protocol defined in the endpoint URL.
Sumo logic endpoint in this case

## Prerequisites

1. Sumo Logic account

## Installation Configuration

**Sumo Logic Setup:**

**Set up an HTTP Source for Catchpoint.**

1. From Sumo Logic, select Manage Data > Collection > Setup Wizard and select Set Up Streaming Data.

	![Sumo Logic Setup : step 1](https://github.com/catchpoint/Integrations.SumoLogic/blob/main/Screenshots/sumo%20step1.png)	

1.  Select Your custom app and chose HTTP source.

	![Sumo Logic Setup : step 2](https://github.com/catchpoint/Integrations.SumoLogic/blob/main/Screenshots/sumo%20step2.png)

1. Enter `Catchpoint-Testdata-Webhooks` for Source Category and click Next, it should start creating an endpoint.

	![Sumo Logic Setup : step 3](https://github.com/catchpoint/Integrations.SumoLogic/blob/main/Screenshots/sumo%20step3.png)

1. Copy the HTTP Source URL that appears on the following page. This will be
required when configuring Catchpoint Test data webhooks. After copying the URL click Next.

	![Sumo Logic Setup : step 4](https://github.com/catchpoint/Integrations.SumoLogic/blob/main/Screenshots/sumo%20step4.png)

**Catchpoint Setup:**

Add the copied URL to Catchpoint.

1.	In catchpoint, from `Settings` go to the [API page](https://portal.catchpoint.com/ui/Content/Administration/ApiDetail.aspx).
2.	Under Test, Data Webhook add the copied URL.
3.	Select default `JSON` for Test-data webhook and save the changes.

_Note : Test data webhook should be enabled under the test properties page._

## Results

**Sample Log Message**

This section provides an example of a JSON Test data webhook sent by Catchpoint agents and logged in Sumo Logic.

`{"Version":4,"V":5,"TestDetail":{"Name":"Site Testing","TypeId":0,"Labels":[{"Version":["v1"]}],"MonitorTypeId":18},"TestId":464062,"ReportWindow":"202102021310","NodeId":540,"NodeName":"Frankfurt, DE - AWS","Asn":16509,"TestRuntime":"20210202131557179","DivisionId":3333,"ClientId":22,"Summary":{"V":1,"Timestamp":"20210202131557179","MonitorVersion":"75.0.3770.90.1","Timing":{"Total":5754,"Connect":8,"Dns":1,"ContentLoad":5724,"Load":4,"Send":0,"Ssl":21,"Wait":705,"Wire":3658,"Client":83,"ContentType":{"Image":5931,"Script":4020,"Html":7715,"Css":314,"Font":219},"DocumentComplete":3741,"DomLoad":1858,"FirstContentfulPaintTime":1821,"FirstPaintTime":1821,"RenderStart":1916,"TimeToInteractive":4228,"VisuallyCompleteTime":2008},"Address":"172.67.168.158","Error":{"Any":1,"LoadObjects":1},"Action":{"CaptureHttpHeaders":1,"CaptureScreenshot":1,"CaptureResponseContent":1},"Byte":{"Response":{"Content":5602,"Headers":1496,"TotalContent":8489873,"TotalHeaders":63639,"ContentType":{"Image":7795966,"Script":517077,"Html":33994,"Css":63659,"Font":142027}}},"Counter":{"Connections":22,"Hosts":21,"FailedRequests":1,"Requests":90,"Cached":4,"Redirections":1,"ContentType":{"Image":45,"Script":17,"Html":8,"Css":8,"Font":5},"FilmstripImages":6,"JsFailures":5},"ContentZones":{"4730":{"V":1,"Timing":{"StartToEnd":5671,"Impact":3571},"Counter":{"Request":86,"Failure":1,"Connection":22,"ResponseBytes":8553512,"Host":21},"Error":50200},"4732":{"V":1,"Timing":{"StartToEnd":5671,"Impact":3571},"Counter":{"Request":86,"Failure":1,"Connection":22,"ResponseBytes":8553512,"Host":21},"Error":50200}},"HostCollections":{"api.curator.io":{"V":1,"Timing":{"StartToEnd":395,"Dns":31,"Connect":89,"Ssl":94,"Wait":176,"Load":5},"Counter":{"Request":1,"Connection":1,"ResponseBytes":3212}},"c.ndtvimg.com":{"V":1,"Timing":{"StartToEnd":69,"Dns":27,"Connect":3,"Ssl":17,"Send":3,"Wait":17,"Load":20},"Counter":{"Request":2,"Connection":1,"ResponseBytes":92219}},"cdn.curator.io":{"V":1,"Timing":{"StartToEnd":1040,"Impact":33,"Dns":23,"Connect":10,"Ssl":27,"Send":11,"Wait":340,"Load":1118},"Counter":{"Request":18,"Connection":1,"ResponseBytes":662539}},"cdnjs.cloudflare.com":{"V":1,"Timing":{"StartToEnd":136,"Dns":31,"Connect":1,"Ssl":62,"Send":2,"Wait":16,"Load":24},"Counter":{"Request":1,"Connection":1,"ResponseBytes":88365}},"f.vimeocdn.com":{"V":1,"Timing":{"StartToEnd":293,"Dns":0,"Connect":2,"Ssl":4,"Send":3,"Wait":38,"Load":453},"Counter":{"Request":3,"Connection":1,"ResponseBytes":166983}},"fonts.googleapis.com":{"V":1,"Timing":{"StartToEnd":128,"Dns":31,"Connect":1,"Ssl":63,"Send":2,"Wait":31},"Counter":{"Request":2,"Connection":1,"ResponseBytes":2133}},"fonts.gstatic.com":{"V":1,"Timing":{"StartToEnd":53,"Dns":0,"Connect":14,"Ssl":17,"Send":1,"Wait":27,"Load":7},"Counter":{"Request":3,"Connection":1,"ResponseBytes":59819}},"fresnel.vimeocdn.com":{"V":1,"Timing":{"StartToEnd":232,"Impact":184,"Dns":0,"Connect":10,"Ssl":4,"Wait":222},"Counter":{"Request":2,"Connection":1,"ResponseBytes":428}},"g.3gl.net":{"V":1,"Timing":{"StartToEnd":1030,"Dns":21,"Connect":14,"Ssl":51,"Send":1,"Wait":598,"Load":345},"Counter":{"Request":1,"Connection":1,"ResponseBytes":34911}},"i.vimeocdn.com":{"V":1,"Timing":{"StartToEnd":43,"Dns":0,"Ssl":4,"Wait":39},"Counter":{"Request":5,"Connection":1,"ResponseBytes":36018}},"ichef.bbci.co.uk":{"V":1,"Timing":{"StartToEnd":33,"Dns":4,"Ssl":13,"Send":3,"Wait":39,"Load":6},"Counter":{"Request":6,"Connection":1,"ResponseBytes":147606}},"images.hindustantimes.com":{"V":1,"Timing":{"StartToEnd":39,"Dns":22,"Ssl":11,"Wait":4,"Load":2},"Counter":{"Request":1,"Connection":1,"ResponseBytes":28329}},"images.news18.com":{"V":1,"Timing":{"StartToEnd":63,"Dns":28,"Connect":1,"Ssl":16,"Send":1,"Wait":4,"Load":13},"Counter":{"Request":1,"Connection":1,"ResponseBytes":73019}},"player.vimeo.com":{"V":1,"Timing":{"StartToEnd":746,"Dns":15,"Connect":6,"Ssl":26,"Wait":328,"Load":1060},"Counter":{"Request":2,"Connection":2,"ResponseBytes":21189}},"test.com":{"V":1,"Timing":{"StartToEnd":5282,"Impact":1186,"Dns":1,"Connect":603,"Ssl":21,"Send":22,"Wait":7125,"Load":4772},"Counter":{"Request":27,"Failure":1,"Connection":1,"ResponseBytes":5723453},"Error":50200},"static.toiimg.com":{"V":1,"Timing":{"StartToEnd":51,"Dns":20,"Connect":2,"Ssl":18,"Wait":5,"Load":6},"Counter":{"Request":1,"Connection":1,"ResponseBytes":32709}},"techcrunch.com":{"V":1,"Timing":{"StartToEnd":50,"Dns":1,"Ssl":7,"Send":5,"Wait":58,"Load":108},"Counter":{"Request":6,"Connection":1,"ResponseBytes":572231}},"vimeo.com":{"V":1,"Timing":{"StartToEnd":149,"Dns":11,"Connect":10,"Ssl":11,"Wait":117},"Counter":{"Request":1,"Connection":1,"ResponseBytes":789}},"www.googletagmanager.com":{"V":1,"Timing":{"StartToEnd":125,"Dns":16,"Connect":3,"Ssl":36,"Send":1,"Wait":45,"Load":24},"Counter":{"Request":1,"Connection":1,"ResponseBytes":35929}},"www.hindustantimes.com":{"V":1,"Timing":{"StartToEnd":49,"Dns":26,"Connect":1,"Ssl":15,"Wait":7},"Counter":{"Request":1,"Connection":1,"ResponseBytes":356}},"www.notebookcheck.net":{"V":1,"Timing":{"StartToEnd":94,"Dns":7,"Connect":1,"Ssl":19,"Send":1,"Wait":36,"Load":30},"Counter":{"Request":1,"Connection":1,"ResponseBytes":771275}}},"Score":{"SpeedIndex":3830},"AverageFramesPerSecond":26.2,"JsFailures":[{"V":2,"LineNumber":479,"Message":"Uncaught TypeError: $(...).dropdown is not a function","Count":4,"URL":"https:\/\/test.com\/"},{"V":2,"LineNumber":7,"Message":"Uncaught ReferenceError: calPerformance is not defined","Count":2,"URL":"https:\/\/test.com\/"},{"V":2,"LineNumber":19,"Message":"Uncaught ReferenceError: skel is not defined","Count":1,"URL":"https:\/\/test.com\/assets\/js\/main.js"}],"Request":"https:\/\/test.com"}`

**Configure the Catchpoint dashboard**

The Catchpoint apps which have a default dashboard are your central location for the Catchpoint tests/apps in your account. View at-a-glance information surrounding your recent Errors, Events, and Alerts. The Node Map provides a geographical overview of your test runs, while the Tests widget lets you search for and quickly access your synthetic data. 

**Install the Catchpoint app for Sumo Logic**

To install the Catchpoint app: 

1.	Sign in to the `Sumo Logic` console. 
2.	Click `App Catalog`. 
3.	Search for ` Catchpoint app` and select the same. 
4.	Select the `version` of the service you're using.
5.	Click `Add to Library`.

**Filter the dashboard**

Click the filter icon in the top-left corner of the dashboard to display a list of filters you can apply across the entire dashboard. Use the filters to drill down and examine the data on a more granular level.

![Dashboard Filters](https://github.com/catchpoint/Integrations.SumoLogic/blob/main/Screenshots/filters.png)

![Dashboard Filters - Dropdown](https://github.com/catchpoint/Integrations.SumoLogic/blob/main/Screenshots/filters%20dropdown.png)

![Overview Dashboard](https://github.com/catchpoint/Integrations.SumoLogic/blob/main/Screenshots/overview.png)

To get more Insights on a particular test, click on the test names this will link to Catchpoint Smart board.

![Test Times Dashboard](https://github.com/catchpoint/Integrations.SumoLogic/blob/main/Screenshots/Test%20times.png)

**Query samples**

You can use the following queries to create or modify your dashboard.

Visualizing DNS Time: 

`_sourceCategory=Catchpoint-Testdata-Webhooks | json field=_raw "Summary.Timing.Dns","NodeName","TestId","TestDetail.Name" as Dns,Node_Name,Test_Id,Test_Name | timeslice 1m | where Test_Name matches /^TestName$/ and Node_name matches /^NodeName$/ | avg (Dns) as Dns  by Node_Name,Test_Id,_timeslice | transpose row _timeslice column  Node_Name,Test_Id`

Make sure to replace the actual `Test Name` and `Node Name` in the above query.

To retrieve other metrics like Connect, Send, Load we can replace the JSON path from the above query.

`json field=_raw "Summary.Timing.Connect" as Connect`  
`json field=_raw "Summary.Timing.Send" as Send`
