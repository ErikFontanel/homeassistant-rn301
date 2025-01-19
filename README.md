
# R-N301 custom component for homeassistant

This custom component allows you to control a Yamaha R-N301 network receiver via Home Assistant.

## Installation

1. Download the repository  
  `git clone git@github.com/ErikFontanel/homeassistant-rn301`  
2. Navigate to the repository you just downloaded.  
  `cd homeassistant-rn301`  
3. Copy the `rn301` folder to the `custom_components` folder in your homeassistant directory.  
  For example, when you're using home assistant OS:  
  `cp -r rn301 /root/config/custom_components/rn301`  
4. Add the 'Yamaha R-N301 integration' by adding it to your `configuration.yaml`:
  ```yaml
  media_player:
    - platform: rn301
      name: "Yamaha R-N301"
      host: {IPADDRESS}
  ```
  Optionally but recommended, add the ip address of the R-N301 to the 'host' key.
5. Restart Home Assistant
[![Open your Home Assistant instance and show your server controls.](https://my.home-assistant.io/badges/server_controls.svg)](https://my.home-assistant.io/redirect/server_controls/)

Now you can control the R-N301 by using the `media_player.yamaha_r_n301` entity or add a card to your Home Assistant dashboard.
```yaml
 - type: media-control
  entity: media_player.yamaha_r_n301
  grid_options:
    columns: 12
      rows: 2
```

## Development

Component development requires libraries for editor and place where new features can be run.

### Libraries

Prepare ubuntu

    sudo apt-get install autoconf libssl-dev libxml2-dev libxslt1-dev libjpeg-dev libffi-dev libudev-dev zlib1g-dev pkg-config
    sudo apt-get install -y libavformat-dev libavcodec-dev libavdevice-dev libavutil-dev libswscale-dev libavresample-dev libavfilter-dev
    sudo apt-get install python3-venv

Install venv - virtual environments for project and place for home assistant libs

    python3.7 -m venv venv
    source venv/bin/activate.fish

Install home assistant libraries - local installation not need special permission and use `sudo`

    python3 -m pip install homeassistant
    
    
### Docker
    
Install home assistant in docker (https://www.home-assistant.io/docs/installation/docker/)

    docker run --init -d --name="home-assistant-rn301" -v /PATH_TO_YOUR_CONFIG:/config --net=host homeassistant/home-assistant:stable

## Contribute

Please do! Open a Pull Request with your improvements.

This project was made possible thanks to the original creator [vrih](https://github.com/vrih/homeassistant-rn301) and the deprecation fixes by [noam148](https://github.com/noam148/homeassistant-rn301) and [yanoosh](https://github.com/yanoosh/homeassistant-rn301). All your great work is greatly appreciated.

