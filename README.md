# Serverless Function

The simple function takes HbA1C values and outputs a response based on tiers listed by [Mayo Clinic](https://www.mayocliniclabs.com/api/sitecore/TestCatalog/DownloadTestCatalog?testId=610441)

- HbA1C `<=4`: **may be of concern, see a doctor** ref range not established for patients <18 year olds
- HbA1C between `4.1 and 5.7`: **Normal**
- HbA1C between `5.8 and 6.4`: **Prediabetic**
- HbA1C `>=6.5`: **Diabetic**

### Cloud environments used & regions

- Azure: Canada Central

- GCP:

### Deployment, execution (URLs and outputs), example requests invocations

- Azure: Listed [here](https://github.com/briggsprashar/504_serverless_function/blob/main/Azure/azure.md)

- GCP: Listed [here](https://github.com/briggsprashar/504_serverless_function/blob/main/GCP/gcp.md)

### Public endpoint URLs (+ notes on auth: unauthenticated vs key‑based)

- Azure
    - [Default domain](https://serverless1-dca6gxfkhadfc0b2.canadacentral-01.azurewebsites.net/)
    - Endpoint URL: https://serverless1-dca6gxfkhadfc0b2.canadacentral-01.azurewebsites.net/api/http_trigger1?(function_key)
    - Authorization: Key-based: Can be toggled as Anonymous as well duting setp, which could be for unauthenticated access ... potentially!! :D

- GCP
    - Endpoint URL:
    - Auth: unauthenticated by default, and can be toggled on during setup and later.

### Short comparison paragraph of the two clouds.





