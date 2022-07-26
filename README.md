# all-about-installations
some installation instructions compiled over the internet. I will keep on adding

### Install intel oneAPI tool kit. See the link below:
https://estuarine.jp/2021/03/install-oneapi/?lang=en

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
