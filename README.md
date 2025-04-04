<span style="font-family: Calibri;">
<h1>Preparations</h1>

<h2>Index used in this repo</h2>

Complete the [ragWorkshop](https://github.com/notanaha/ragWorkshop) repository to build the index used in this repository.
<br>The index name and field refer to the same names used in ragWorkshop.
<br><br>
<h2>Create a conda environment</h2>

```bash
conda create -n pf310 python=3.10
conda activate pf310
```

<h2>Install required packages</h2>

```bash
pip install -r requirements.txt
```

If above command failed 
```bash
pip install --no-build-isolation --no-cache-dir -r requirements.txt
```

<h2>Setup config.json file</h2>

Edit **.azureml/config.json**

<h2>Install Pre-release version of promptflow extension</h2>
<img src="./image/SwitchToPreReleaseVersion.png">

<h2>Create connections</h2>

```bash
pf connection create -f ./connections/azure_openai.yml
```
Optional (not used in the following flow.dag.yaml)
```bash
pf connection create -f ./connections/cognitive_search.yml
```

<h2>Edit flow.dag.yaml</h2>

Edit **flow.dag.yaml**
- <###aoai_local_connection_name###>
- <###subscription_id###>
- <###rg_name###>
- <###ws_name###>
- <###aisearch_connection_name###>

<h2>Optional - login to Azure</h2>

```bash
az login [--tenant=<tenant_id>]
az configure --defaults group=<resource_group_name> workspace=<workspace_name>
```

</span>