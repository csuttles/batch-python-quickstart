---
page_type: sample
description: "A basic Python application that introduces Batch features such as pools, nodes, jobs, tasks, and interaction with Storage."
languages:
- python
products:
- azure
---

# Fork of a Quickstart
The intent of this repo is to demonstrate how a quickstart can be turned into something more useful, with very little change. It's based on / related to my blog article, here:
https://blog.csuttles.io/extending-the-azure-batch-python-quickstart/

## OK, what does it do?
This batch example extends the quickstart by customizing the batch node for our use by installing exiftool. With exiftool installed we can extract GPS Position for all the photos in our blob storage container, and use that GPS Position to output a link to a map for the location of the picture. This script create a blob storage container, and will then upload the photos in the `img` dir (along with any `.jpg` files you add there). Once photos are uploaded, it will create a pool and batch group based on out specification and run the job. One exit, it will clean up any resources provisioned by the script.

This script still requires setup of a Storage Account and Batch Account. You need to set those up first, so you can populate the details of `env.sh`

## Setup
The file `env.sh` has all the variables you need to provide and export.
### venv
Create a venv within the base of the repo. Here's an example:
```
python3 -m venv --copies venv
source venv/bin/activate
pip install -r src/requirements.txt
```
### Run the job
Run the job with the following commands, from the terminal where you have exported your Azure related variables and also activated your venv
```
cd src
time python python_quickstart_client.py
```

## Where will I get GPS tagged images?
They are already here for you! You can find sample photos in the `img` dir.

## Why did you put binaries in git?
I did it to make this all self contained. I know better but I did it anyway so that this could be very easy for people to experiment with.

---

# Azure Batch Python Quickstart

A basic Python application that introduces Batch features such as pools, nodes, jobs, tasks, and interaction with Storage. Each task writes a text file to standard output.

For details and explanation, see the accompanying article [Run your first Batch job with the Python API](https://docs.microsoft.com/azure/batch/quick-run-python).

## Prerequisites

- Azure Batch account and linked general-purpose Azure Storage account
- Python 2.7 or 3.3 or later including pip

## Resources

- [Azure Batch documentation](https://docs.microsoft.com/azure/batch/)
- [Azure Batch code samples](https://github.com/Azure/azure-batch-samples)

## Project code of conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
