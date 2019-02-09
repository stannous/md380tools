# MacOS  specifics #

## Preparing build environment ##

#### With Homebrew: ####

    brew update
    brew upgrade
    brew install binutils libusb
    brew cask install gcc-arm-embedded # This is where you get the ARM cross-compiling stuff
    # Since Mojave users will not be able to find gcc-arm-embedded,
    # they will need to do the following
    #    brew tap PX4/homebrew-px4
    #    brew update
    #    brew install -v gcc-arm-none-eabi
    sudo easy_install pip
    sudo pip2 install pyusb

#### Fix the environment statements: ####

The scripts look for python2, but you likely just have that installed as (system) python. Hence:

    sudo ln -s /usr/bin/python /usr/bin/python2

After this, `make flash` as expected.
  
