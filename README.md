# Serverless Function

## Source

The simple function takes HbA1C values and outputs a response based on tiers listed by [Mayo Clinic](https://www.mayocliniclabs.com/api/sitecore/TestCatalog/DownloadTestCatalog?testId=610441)

- HbA1C `<=4`: **may be of concern, see a doctor** ref range not established for patients <18 year olds
- HbA1C between `4.1 and 5.7`: **Normal**
- HbA1C between `5.8 and 6.4`: **Prediabetic**
- HbA1C `>=6.5`: **Diabetic**

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

## GCP and Azure Comparision





