# Coffee-Factory

# How to set up the project:



###  Designer: 

- Clone the repository to a desired location
- If you do not have Apama on your machine, use this link to download it: 
  https://download.cumulocity.com/Apama/ (full edition)
- Open the Project via Eclipse



### Prometheus:

- Go to https://prometheus.io/download/ and download Prometheus (should be on the very top) by choosing the file that corresponds to your OS.
- Install Prometheus to a suitable directory.
- Go to the folder which contains the installation and open the prometheus.yml file by right clicking on it and select a suitable text reader(notepad might not work), for example, I use Notepad++ to open it. Another thing you can do to open the file is: drag and drop the prometheus.yml file onto Designer.
- Once opened, at the very bottom make sure it looks like this:

    static_configs:
    - targets: ['localhost:15903']

  You will have to just set the 'targets' to ['localhost:15903'];



 
### Grafana:

Firstly, follow this link: https://grafana.com/docs/guides/getting_started/
- Once you do the first two steps i.e. installation guide & logging in for the first time,
open the folder 'Grafana' in your Designer project and in it you would see a grafana.json file, copy the content of the file.
- Go to Grafana, click 'Create' (the plus button at the top left corner) and then click 'dashboard settings' (on top right) which will take you to another page.
- In that page click JSON model, paste here what you copied from the grafana.json file in Designer project.
- Scroll to the top of the JSON model text and change the value of the 'id' to be 'null' (without quotes);
- Click 'Save Changes'.

- Now go to 'Configuration'
- Click on the Prometheus field (should be in the center of the screen);
- Update the URL to: http://localhost:9090
- Update the Scrape Interval to 1s


-   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -   -


# To start the project:
- In Eclipse, right click on the project folder.
- Select 'Run as'
- Select 'Apama Application'

In about couple of seconds the live data will be displayed on Grafana.

And if you would like to send a bad event go to Designer. Find the coffee project and start it if it is not on. Open the events folder and you will see a BadEvent.evt file. Right-click on it and select Apama -> Send Events. Now observe how Apama will handle the bad event on Grafana.

![alt text](https://github.com/POBnH4/Coffee-Factory/blob/master/BlogFinal.png)




