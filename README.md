# Serverless Function

## Source

The simple function takes HbA1C values and outputs a response based on tiers listed by [Mayo Clinic](https://www.mayocliniclabs.com/api/sitecore/TestCatalog/DownloadTestCatalog?testId=610441)

- HbA1C `<=4`: **may be of concern, see a doctor** ref range not established for patients <18 year olds
- HbA1C between `4.1 and 5.7`: **Normal**
- HbA1C between `5.8 and 6.4`: **Prediabetic**
- HbA1C `>=6.5`: **Diabetic**

## Videos

<details>
  <summary>Video 1: GitHub ☁️</summary>  
<br />
<div>
  <a href="https://www.loom.com/share/e7c2411119bf4715b6cf5ed6bbca3979" target="_blank" style="float: left;">
    <img style="max-width:200px;" src="https://cdn.loom.com/sessions/thumbnails/e7c2411119bf4715b6cf5ed6bbca3979-b5b70dca1be94f7a-full-play.gif" />
  </a>
  <div style="clear: both;"></div>
</div>
</details>

<br />

<details>
  <summary>Video 3: Quick Walkthrough ☁️</summary>  
<br />
<div>
  <a href="https://www.loom.com/share/206d87acf52f43499cb652ebf7d92d41" target="_blank" style="float: left;">
    <img style="max-width:200px;" src="https://cdn.loom.com/sessions/thumbnails/206d87acf52f43499cb652ebf7d92d41-e7b1a8b684cff848-full-play.gif" />
  </a>
  <div style="clear: both;"></div>
</div>
</details>

<br />

<details>
  <summary>Video 2: GCP ☁️</summary>  
<br />
<div>
  <a href="https://www.loom.com/share/5fd55f9054ea49c6ad6b0811a287ead4" target="_blank" style="float: left;">
    <img style="max-width:200px;" src="https://cdn.loom.com/sessions/thumbnails/5fd55f9054ea49c6ad6b0811a287ead4-8751a2db221c2fc3-full-play.gif" />
  </a>
  <div style="clear: both;"></div>
</div>
</details>

## Environments & Regions

> Azure: **Canada Central**

> GCP: **Europe-West1**

## Deployment Kitchen Sink

> Azure: Listed [here](https://github.com/briggsprashar/504_serverless_function/blob/main/Azure/azure.md)

> GCP: Listed [here](https://github.com/briggsprashar/504_serverless_function/blob/main/GCP/gcp.md)

## Endpoint URLs

### Azure

> [Default domain](https://serverless1-dca6gxfkhadfc0b2.canadacentral-01.azurewebsites.net/)

> Endpoint URL: https://serverless1-dca6gxfkhadfc0b2.canadacentral-01.azurewebsites.net/api/http_trigger1?(function_key) 
<br /> **WITH KEY**

> Authorization: **Key-based** by default. <br />Can be toggled as Anonymous as well during setup and later.

### GCP

> [Endpoint URL](https://serverless1-970719512702.europe-west1.run.app) <br /> **NO KEY**

> Authorization: **Unauthenticated** by default. <br />Can be toggled on during setup and later.

## Short comparision

> The 2 sections below will establish a more robhust comparision. In short, for traditional industries Azure functions etc seem better. The fact that Azure has authentican by default, and GCP does now, also hints at the different use cases the two target. Azure seems to be more for regulated and hard-wired legacy-based use-cases. Experience-wise, Azure seems more intitutive to work with. It seems Oracle would be even more "brick and mortar" because it is widely used in US heathcare. It'd be a good idea to also compare it with Azure and GCP.

## Deepdive

<details>
<summary>Comparision</summary>

<br />

> Credit: Got most of the content in the table below from an LLM to better understand the differences bewteen Azure and GCP.

| Feature                | GCP (Cloud Functions)                  | Azure Functions                          |
|------------------------|----------------------------------------|------------------------------------------|
| **Execution Model**        | Stateless, auto-scaled (Automatically spins up instances per request, ensuring simplicity and isolation.)                | Stateless, Durable Functions (for workflow orchestration and maintaining state)   |
| **Language Support**       | Node.js, Python, Go, Java, .NET, Ruby, PHP (many popular ones here)| C#, JavaScript, Java, Python, PowerShell, TypeScript, F#, custom (Mostly support Microsoft developers)|
| **Deployment Tools**       | gcloud CLI, Console, Cloud Build  (designed for straightforward cloud-native deployments.) | Visual Studio, VS Code, Azure CLI, DevOps, GitHub Actions ( integrates tightly with Microsoft tooling.)|
| **Triggers** | HTTP, Pub/Sub, Cloud Storage (primarily event-driven via GCP services)| HTTP, Event Grid, Timer, Storage, others (tight integrations with MSFT tooling)|
| **State Management**       | Stateless only                          | Durable Functions orchestration and state|
| **Cold Start Optimization**| Simplicity prioritized, less optimized  | Premium Plans enable **pre-warming**         |
| **Integration Approach**   | Manual via code                         | **Declarative bindings**, configuration      |
| **Unique Strength** | Minimalistic, HTTP-native, rapid dev (ideal for lightweight microservices) | State orchestration & MS ecosystem (builtin) |
| **Code Editor** | Web inline editor in console & Cloud Shell Editor (VS Code based) | VS Code, Visual Studio, Azure Portal editor, browser UI|
| **Testing**  | Local unit tests possible, emulator, manual HTTP tests via UI/CLI | Local test with VS Code, Azure CLI, Azure Function Core Tools |
| **Deployment** | Thru gcloud CLI, Cloud Console, Cloud Build pipelines, GitHub Actions | Visual Studio, VS Code, Azure CLI, DevOps, GitHub Actions|
| **Autosave in Editor**  | Console editor has autosave, Cloud Shell Editor supports VS Code-like autosave | VS Code/Visual Studio has autosave, browser editor supports  |
| **Logging** | Cloud Logging (Stackdriver), log viewer in console, real-time via logging API | Azure Monitor, Application Insights, log streaming in portal  |
| **Execution Model** | Stateless, auto-scaled | Stateless; Durable Functions for state|

</details>

<br />

<details>
 <summary>Narratitve</summary>
<br />

> Functions in GCP and Azure are both solid options for serverless computing. GCP is not that well suited for traditonal industries like education and helthcare though.

> While **GCP** is all about simplicity and speed, its "stateless" and auto-scalability is conducive more for web/mobile apps/use-cases, especially offering support for many popular programming languages, easy deployment tools like the gcloud command line and web console. But to connect GCP functions and services to other services, the codng etc will ahve to be done separately.  

> **Azure** Functions can handle more complex tasks that need to remember progress over time with special features for managing workflows supporting a wide range of triggers working really well with Microsoft’s own tools; eg. Visual Studio. Reliability in runs seems to be better in Azure.   

> Both platforms let you test your code locally, save your work automatically, and provide strong logging to track what’s happening. I did not like GCP's testing UI; clink out of the test (backlog) window and you have to start over again!. Annoying!

> For traditional sectors like healthcare and education, Azure Functions tends to be more suitable due to its strong support for stateful workflows and deep integration with Microsoft’s ecosystem, which many organizations in these sectors already use (MSFT has been around longer "first-mover advantage" and is really visible in legacy tech driven traditional industries). 
 > **Azure Strengths** inlude: managing complex workflows and orchestrating multi-step processes. These are keys for regulated environments and applications that require reliable state management and robust tooling.

> Google Cloud Functions, while simpler and excellent for lightweight, event-driven tasks, is more focused on stateless operations and web/mobile backends. As stated above, GCP may require additional custom work to handle complex workflows or integration-heavy use cases common in healthcare and education.

> Overall, Azure Functions are a richer feature set around state management, triggers, and integration tools gives it an edge for traditional sectors needing reliable, scalable, and maintainable serverless solutions.

</details>


