# all-about-installations
some installation instructions compiled over the internet. I will keep on adding

## Install intel oneAPI tool kit

###Install the required drivers
#### Add package repository
sudo apt-get install -y gpg-agent wget

wget -qO - https://repositories.intel.com/graphics/intel-graphics.key | sudo apt-key add -

sudo apt-add-repository 'deb [arch=amd64] https://repositories.intel.com/graphics/ubuntu focal main'

##### Install run-time packages
sudo apt-get update
sudo apt-get install intel-opencl-icd intel-level-zero-gpu level-zero intel-media-va-driver-non-free libmfx1

#### OPTIONAL: Install developer packages
sudo apt-get install libigc-dev intel-igc-cm libigdfcl-dev libigfxcmrt-dev level-zero-dev

#### If you are using GPU, use the following; else ignore

stat -c "%G" /dev/dri/render*

### Install Intel oneAPI

#### Work in the directory /tmp, which is accessible to both user and root.

cd /tmp

wget https://apt.repos.intel.com/intel-gpg-keys/GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

sudo apt-key add GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

rm GPG-PUB-KEY-INTEL-SW-PRODUCTS.PUB

echo "deb https://apt.repos.intel.com/oneapi all main" | sudo tee /etc/apt/sources.list.d/oneAPI.list

sudo apt update

#### Specify the packages to install. [Here](https://www.intel.com/content/www/us/en/develop/documentation/installation-guide-for-intel-oneapi-toolkits-linux/top/installation/install-using-package-managers/apt.html#pkgtable) Base Toolkit and HPC Toolkit were installed. Installation of Base Toolkit took a long time.

sudo apt install intel-basekit

sudo apt install intel-hpckit

### The installation directory is /opt/intel/oneapi.

#### Configuration for Intel compilers

#### To use the Intel compilers, execute the following. Appending this to ~/.bashrc will save you the trouble of running it every time.

source /opt/intel/oneapi/setvars.sh

#### Check your installation:

ifort --version

icc --version

icpc --version

