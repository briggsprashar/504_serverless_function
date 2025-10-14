# GCP Function

## Create

<details>
<summary>Steps</summary>

1. Login to a porovisioned Google Cloud Console acct
2. In search bar, search for Functions > select "Cloud Run Functions"
3. Select "Write a function"
4. Select "Use an inline editor to create a function"
    - This s simple function, so docker creation and artifact registry is not needed.
    - Github connection is also not needed.
5. Configure the function to basics for this function: Python, and basic setup.

</details>

## Function code

<details>
<summary>Code</summary>

```bash
import functions_framework

@functions_framework.http
def hba1c(request):
    request_args = request.args
    request_json = request.get_json(silent=True)

    if request_args and 'hba1c' in request_args:
        hba1c_str = request_args['hba1c']
    elif request_json and 'hba1c' in request_json:
        hba1c_str = request_json['hba1c']
    else:
        hba1c_str = None

    try:
        hba1c = float(hba1c_str) if hba1c_str else None
    except ValueError:
        hba1c = None

    if hba1c is not None:
        if hba1c < 5.7:
            status = "NORMAL (You Are Free From Diabetes)"
        elif 5.7 <= hba1c <= 6.4:
            status = "You Are Prediabetic"
        else:
            status = "ABNORMAL (You Have Diabetes)"
        message = f"Your HbA1c level is {hba1c}%. Which means \n{status}"
    else:
        message = (
            "This HTTP triggered function executed successfully.\n"
            "Enter a 'hba1c' value in the query string or request body to receive an interpretation."
        )

    return message
```
</details>

## Test & Deploy

<details>
<summary>Steps</summary>

<br />

> Function Console 

<br />

<img src="./gcp_images/g3functioncode.png" alt="Function Source Code" width="600">

<br />

> Function Test 

<br />

<img src="./gcp_images/g4.1test_service.png" alt="Test" width="500">

<br />

> Function CLI Test

<br />

<img src="./gcp_images/g5test_cli.png" alt="Test CLE" width="700">

<br />

> URL deployed

<br />

<img src="./gcp_images/g4urldeployed.png" alt="URL deployed" width="700">

<br />

</details>

## Run & validate

<details>
<summary>Test</summary>

<br />

> GCP CLI run

<br />

<img src="./gcp_images/g5test_cli.png" alt="CLI run" width="700">

<br />

> URL run

<br />

<img src="./gcp_images/g5url_testresponse.png" alt="URL run" width="500">

<br />

> Google Colab Run with **REQUESTS INVOCATION CODE**

<br />

<img src="./gcp_images/g6colab_run.png" alt="Colab run" width="700">

</details>

## Monitor

<details>
<summary>Logging</summary>

<br />

> Function log

<br />

<img src="./gcp_images/g8logs.png" alt="Function log" width="700">

<br />

> Logs explorere with Gemini

<br />

<img src="./gcp_images/g7logging_withgemini.png" alt="Colab run" width="700">

<br />

> Recent Logs

<br />

<img src="./gcp_images/g9logrecent.png" alt="Colab run" width="700">

</details>

<br />

<details>
<summary>Monitor & Manage</summary>

<br />

> Synthetic monitoring

<br />

<img src="./gcp_images/g10synthetic_monitoring.png" alt="Function log" width="700">

<br />

> YAML mannual configuration

<br />

<img src="./gcp_images/g11yaml_manuallyconfigure.png" alt="Function log" width="700">

<br />

> YAML metadata

<br />

<img src="./gcp_images/g12yaml_metadata.png" alt="Function log" width="700">

<br />

> YAML container data

<br />

<img src="./gcp_images/g13yaml_containersdata.png" alt="Function log" width="700">

<br />

> YAML traffic

<br />

<img src="./gcp_images/g14yaml_traffic_etc..png" alt="Function log" width="400">

<br />

> Revisions > Account

<br />

<img src="./gcp_images/g16revisions_account.png" alt="Function log" width="700">

<br />

> Observability > Annotations

<br />

<img src="./gcp_images/g17observability_annotations.png" alt="Observability > Annotations" width="700">


</details>

<br />


## Security

<details>
<summary>Authentication</summary>

<br />

> Both Azure and GCP have options to authenticate; Where Auzre has it by default, GCP has open-access by default. This can be toggled either way in both.

<br />

<img src="./gcp_images/g15security_auth.png" alt="Function log" width="700">

</details>