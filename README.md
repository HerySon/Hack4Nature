# Project Description

This project was initiated by le [Donut Infolab](https://www.ledonut-marseille.com/) a french association who launched a series of *hackathon* about biodiversity, [Hack4nature](https://www.hackfornature.com/). This project address the [Challenge 4 about Tree Detection](https://www.hackfornature.com/blog/challenge-4-detect-tree), aiming to provide an **open-source individual tree detection tool** based on machine learning algorithms. 

The motivation behind this tool is to help cities in the management of urban plants inventory and encourage citizens to contribute to this tool to add information on this topic, particularly by helping to annotate new images to enrich the training dataset for machine learning algorithms.

The work presented here is a first iteration which provide a prototype of tree identification from satellite images of Marseille city. The prototype is a web page running at [this adress](https://projet-hack4tree-batch-610.herokuapp.com/) mainly developped by one of my data science student's group @LeWagon Marseille and extended by contributors of the tech communtity of [Data for Good Provence](https://www.meetup.com/fr-FR/Data-for-Good-Provence/).

### Model
To perform the task of tree identification, we used a pre-trained deep neural network model called [DeepForest](https://deepforest.readthedocs.io/en/latest/landing.html) implemented with pytorch in a package distributed in [this repository](https://github.com/weecology/DeepForest). DeepForest  uses a deep learning object detection networks, trained on RGB images tree from the National Ecological Observatory Network (USA) which predict bounding boxes of individual trees crowns.
In order to achieve more generalizable detection, we fine-tuned DeepForest on tree images acquired from satellite images of various région of Marseille city (France).

### Data sources
Data were acquired from satellite images of Marseille city by requesting two differents API:
- Google Maps API
- Bing API
<!-- ToDo: Rajouter la 3e API (MapBOx) utiliser pour les requetes -->

### Prototype architecture
As a first iteration, the python code used for this prototype was packaged into a docker image, deployed on Google Cloud Run. 
A web interface, made with the python package [Streamlit](https://streamlit.io/), was deployed on Heroku server, using an API (made with [FastAPI](https://fastapi.tiangolo.com/)) to query the deep learning model predictions. 

### Contributors
- Abib Alimi
- Ahmed Blidia
- Louis Lahmadi
- Alexandre Perdomo
- Nicolas Rochet

### Bibliography
Lot of work have already been proposed for tree dectection, but few applicable to images taken from Marseille's region. See the [Hack4Nature proejct page](https://hack4nature.slite.com/p/note/Fs34nEyzDG61edEM5oHnUF/Challenge-4-Detect-Tree) for details on state of the art and similar project

<!-- Some project note to be detailled cleaned 
- Important links: https://developers.google.com/maps/documentation/urls/get-started#map-action
- conserning the google map api: the price of 1 kilo request is 1,6... dollar, the maximum size of a request map is explained in this text:
*" Image sizes
The size parameter, in conjunction with center, defines the coverage area of a map. It also defines the output size of the map in pixels, when multiplied with the scale value (which is 1 by default).

This table shows the maximum allowable values for the size parameter at each scale value.

scale=1|	scale=2

640x640|	640x640 (returns 1280x1280 pixels)
"
reference: https://developers.google.com/maps/documentation/maps-static/start#Imagesizes
price is taken from the google cloud account
superficies de marseille: 240.6 KM²
-->

<!-- Pre-requirements
# Startup the project

The initial setup.

Create virtualenv and install the project:
```bash
sudo apt-get install virtualenv python-pip python-dev
deactivate; virtualenv ~/venv ; source ~/venv/bin/activate ;\
    pip install pip -U; pip install -r requirements.txt
```

Unittest test:
```bash
make clean install test
```

Check for Hack4Nature in gitlab.com/{group}.
If your project is not set please add it:

- Create a new project on `gitlab.com/{group}/Hack4Nature`
- Then populate it:

```bash
##   e.g. if group is "{group}" and project_name is "Hack4Nature"
git remote add origin git@github.com:{group}/Hack4Nature.git
git push -u origin master
git push -u origin --tags
```

Functionnal test with a script:

```bash
cd
mkdir tmp
cd tmp
Hack4Nature-run
```
-->
# Install

Create a python3 virtualenv and activate it:

```bash
sudo apt-get install virtualenv python-pip python-dev
deactivate; virtualenv -ppython3 ~/venv ; source ~/venv/bin/activate
```

Clone the project and install it:

```bash
git clone git@github.com:{group}/Hack4Nature.git
cd Hack4Nature
pip install -r requirements.txt
make clean install test                # install and test
```
Functionnal test with a script:

```bash
cd
mkdir tmp
cd tmp
Hack4Nature-run
```

# Licence

# Contributing
