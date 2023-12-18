# Local models using Ollama
This directory contains examples using local models with Ollama and Langchain.

# Setup
## Install Ollama
Ollama makes running local LLMs very easy. Just download it from [ollama.ai](https://ollama.ai) and follow the instructions to set it up.
Then, you can run the LLMs in this directory by running `ollama run <model_name>`. Some popular models include: `llama2`, `mistral`, `dolphin-mixtral`, etc.
Please note the memory requirements for these models, e.g. `llama2` 7b models require at least 8GB of RAM, 13b models require at least 16GB of RAM, 70b models require at least 64GB of RAM.
```shell
ollama run llama2
```

## Create a new virtual environment and install dependencies
If you have set up Python using [Anaconda](https://www.anaconda.com/download) or [Miniconda](https://docs.conda.io/projects/miniconda/en/latest/miniconda-install.html), we can use `conda` to create a new virtual environment.
Notes:
   * as of this writing, chromadb does not support Python 3.12, so we will use Python 3.11.5.
   * not all the packages are available on conda default channel, we are using community channel `conda-forge` for those packages
   * not all the packages are available on conda, even on `conda-forge`, we will use `pip` to install those packages
```shell
conda create -n ollama python=3.11.5
conda activate ollama
conda install -c conda-forge langchain chromadb bs4 pypdf
pip install gpt4all langchainhub
```

## Set up development environment
Two of the popular IDEs are [PyCharm](https://www.jetbrains.com/pycharm/) and [VSCode](https://code.visualstudio.com/).
For PyCharm, you can add a new Python SDK and point to conda environment `ollama` created above. Then, all the dependencies will be available in the IDE. See this [guide](https://www.jetbrains.com/help/pycharm/conda-support-creating-conda-virtual-environment.html) for more details.
For VSCode, install the python plugin and select conda environment `ollama` as the Python interpreter. See this [guide](https://code.visualstudio.com/docs/python/environments) for more details.

# Examples
   * *hello.py:* a simple example to show how to use Langchain to generate text from a local model
   * *rag.py:* a simple example to show how to use Langchain to generate text from a local model and a Web retriever

# References
    * [Ollama](https://ollama.ai)
    * [Langchain with Ollama](https://python.langchain.com/docs/integrations/llms/ollama)
    * [Langchain with Ollama Tutorial](https://github.com/jmorganca/ollama/blob/main/docs/tutorials/langchainpy.md)