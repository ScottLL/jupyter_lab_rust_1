# Rust Notebook
![Screenshot 2023-03-26 at 12 29 22 AM](https://user-images.githubusercontent.com/43226003/227755372-c1404024-2dd4-4873-b4e9-e4f496986d48.png)

# install Minicoda 
(check your minicoda version on https://docs.conda.io/en/latest/miniconda.html)

> wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
> chmod +x Miniconda3-latest-Linux-x86_64.sh
> ./Miniconda3-latest-Linux-x86_64.sh


# create and configure our condo environment
> conda create -n darn python=3 (“darn” (Data Analytics with Rust Notebooks))
> conda env list (find out where the darn path)
> conda activate darn (<path/to/env>)

# Install Packages
> conda install -c conda-forge

If we get -bash: jupyter: command not found
So let's fix that. Let's install Jupyter Lab and use the -y option which automatically says "yes" to any questions asked during the installation process.
> conda install -c conda-forge jupyterlab=2.2.9
> conda install -c anaconda cmake -y
> conda install -c conda-forge nodejs=15 -y

# Install Jupyer Lab Extensions
There's one last thing we need to do before we move on, and that's installing any Jupyter Lab extensions that we may need. One particular extension that we need is the plotly extension, which will allow our Jupyter Notebooks to render our Plotly visualisations. Within your conda environment, simply run the following command:

> jupyter labextension install jupyterlab-plotly

This may take some time, especially when it builds your jupyterlab assets, so keep an eye on it until you're returned control over the conda prompt.

Optionally, you may wish to install the purple looking theme from Figure 1 above.
> jupyter labextension install @shahinrostami/theme-purple-please

# Install Rust
> curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
find more rust doc here: https://www.rust-lang.org/tools/install

You will be given instructions for adding Cargo's bin directory to your PATH environment variable.
> source $HOME/.cargo/env> 
> export PATH="$HOME/.cargo/bin:$PATH"


# Install the EvCxR Jupyter Kernel
This is what will allow us to execute Rust code in a Jupyter Notebook.
> cargo install evcxr_jupyter --version 0.5.3
> evcxr_jupyter --install
> jupyter lab
