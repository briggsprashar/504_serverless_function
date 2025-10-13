# Azure Function

## Creation

<details>
<summary>Create</summary>

<img src="./azure_images/a1.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a2.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a3.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a4.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a5.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a6.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a7.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a8.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a9.png" alt="Creating Azure Function" width="300">
<br />

<img src="./azure_images/a10.png" alt="Creating Azure Function" width="200">

</details>
<br />

## Validation and Invocation

<details>
<summary>Validate</summary>

<br />

<img src="./azure_images/upandrunning.png" alt="Function creted" width="800">

<br />

<img src="./azure_images/a11.png" alt="Function creted" width="700">


<br />

<img src="./azure_images/a12_colab.png" alt="Function creted" width="800">

<br />

> #13 was feeling unlucky!

<br />

<img src="./azure_images/a14.png" alt="Google Colab" width="800">

<br />

**Google Colab: Azure Invocation Code**

```bash
import requests

BASE_URL = "https://serverless1-dca6gxfkhadfc0b2.canadacentral-01.azurewebsites.net/"
FUNCTION = "http_trigger1"
KEY = "enter auto generated key here"

url = f"{BASE_URL}/api/{FUNCTION}"
params = {"hba1c": "5", "code": KEY}

print(url)
print(params)

azure_response = requests.get(url, params=params, timeout=20)

print(azure_response.status_code)
print(azure_response.text)
```
</details>
<br />

<details>
<summary>Log</summary>

<br />
<img src="./azure_images/a16logs.png" alt="Log" width="800">
<br />

</details>
<br />

## Function Run & Test

<details>
<summary>Test</summary>

<br />

> HbA1C = 4

<img src="./azure_images/test1.png" alt="Function test" width="300">

<br />

> HbA1C = 5

<img src="./azure_images/test2.png" alt="Function test" width="300">

<br />

> HbA1C = 6

<img src="./azure_images/test3.png" alt="Function test" width="300">

<br />

> HbA1C = 7

<img src="./azure_images/test4.png" alt="Function test" width="300">

<br />
</details>


