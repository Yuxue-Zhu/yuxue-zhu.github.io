# yuxue-zhu.github.io
# Penguin Data Analysis
This repository contains two computational posts analyzing the
`palmerpenguins` dataset: one written in R and one written in Python.

## Requirements

Install the following before cloning and building the repository.

* **Quarto:** `1.10.18`
* **uv:** `0.12.7`
* **R:** `1.2.4`
* **Git:** `2.50.1`

The R dependencies are managed with `renv`. You do not need to install
`renv` separately; the project will bootstrap it automatically.

The Python dependencies are managed with `uv`.

You can check your installed versions with:

```bash
quarto --version
uv --version
git --version
```

## Reproduce the project

### 1. Clone the repository

Run this command in your **terminal** from the directory where you want to
store the project:

#### SSH

```bash
git clone git@github.com:Yuxue-Zhu/yuxue-zhu.github.io.git
cd yuxue-zhu.github.io
```

#### HTTP
```bash
git clone https://github.com/Yuxue-Zhu/yuxue-zhu.github.io.git
cd yuxue-zhu.github.io
```

### 2. Restore the R environment

Open **R console** from the repository root, run following r command to install required packages in your r environment.

```{r}
renv::restore()
```

### 3. Restore the Python environment

Run the following command in your **terminal** from the repository root:

```bash
uv sync
```

This creates or updates the Python environment using the dependencies
specified by the project.

### 4. Render the Quarto site

Run this command in your **terminal** from the repository root:

```bash
uv run quarto render
```

Quarto will execute the computational posts and build the complete website which is created in **docs** folder. 

These two blogs are located in ***docs/posts/palmerpenguins-python/index.html*** and ***docs/posts/palmerpenguins-r/index.html*** respectively.

### 5. Open it locally

Run this command in your **terminal** from the repository root:

```bash
uv run quarto preview
```
It will open the website in your browser locally at http://localhost:4463/. The port number may different.

## Data

The analyses use the **Palmer Penguins** dataset.

The dataset and documentation are available from:

https://allisonhorst.github.io/palmerpenguins/

The original data were collected by Dr. Kristen Gorman and the Palmer
Station Long Term Ecological Research Program in Antarctica.

## Network requirements

The build **does require network access** if the Python environment has not
already been set up and its dependencies need to be downloaded with `uv`.

The R environment may also need network access the first time `renv::restore()`
is run, because required R packages may need to be downloaded.

Once the environments and dependencies have been restored, the Quarto build
does not need to download the dataset from the internet.

The Python analysis loads the Palmer Penguins data through the
`palmerpenguins` Python package and R library, so the package must be available in the
restored environments.
