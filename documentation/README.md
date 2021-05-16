
# Installation

Board details:

kris@TIA:~/ros2_eloquent$ cat /etc/nv_tegra_release 

# R32 (release), REVISION: 5.1, GCID: 26202423, BOARD: t210ref, EABI: aarch64, DATE: Fri Feb 19 16:45:52 UTC 2021


## General Updates

sudo apt-get upgrade

Did not 

sudo apt autoremove

Wasn't sure the were actually unneded.

## Git

## Robot Operating System

https://developer.nvidia.com/blog/implementing-robotics-applications-with-ros-2-and-ai-on-jetson-platform-2/

https://github.com/dusty-nv/jetson-containers

Need to look into parameter passing, whether minikube is a good idea for modular deployment of mycroft as well.

## Mycroft

https://mycroft.ai/

Instructions for install and debug mode are here:

https://github.com/MycroftAI/mycroft-core

Once it is installed you will need to add skills for TIA to perform it's various use cases by text-to-speech.

### Getting Started

cd ~/
git clone https://github.com/MycroftAI/mycroft-core.git
cd mycroft-core
bash dev_setup.sh

### Start up 

cd ~/mycroft-core
./start-mycroft.sh debug

I'm connected to the internet and need to
be activated. Open your browser and visit
home dot mycroft dot A I to register this
device.

Added to account as TIA. WJRHLA. 

### Configuration

We want TIA to manage its own voice commands. Built local. Here is contents for a ~/.mycroft/mycroft.conf

{
  "skills": {
    "blacklisted_skills": [
      "mycroft-configuration.mycroftai",
      "mycroft-pairing.mycroftai"
    ]
  }
}

Mycroft will then be unable to perform speech-to-text conversion, so you'll need to set that up as well, using one of the STT engines Mycroft supports.

You may insert your own API keys into the configuration files listed above in Configuration. For example, to insert the API key for the Weather skill, create a new JSON key in the configuration file like so:

{
  // other configuration settings...
  //
  "WeatherSkill": {
    "api_key": "<insert your API key here>"
  }
}
API Key Services
These are the keys currently used in Mycroft Core:

STT API, Google STT, Google Cloud Speech
Weather Skill API, OpenWeatherMap
Wolfram-Alpha Skill

# Configuration



# Ongoing Development

It's a good idea to add devtools to the TARS leg in case code changes are in order and there isn't a laptop handy.

## Arduino IDE

