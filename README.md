[![Contributors][contributors-shield]][contributors-url]
[![Issues][issues-shield]][issues-url]

[![alt_text](https://vinepair.com/wp-content/uploads/2015/08/hops-and-beer-social.jpg)](https://vinepair.com/wp-content/uploads/2015/08/hops-and-beer-social.jpg)
<br/>*Image Source: VinePair*
<br />
<!---
<div align="center">
  <a href="https://github.com/rc-9/tools1_project">
    <img src="beerhops.png" alt="Logo" width="80" height="45">
  </a>
-->



<h1 align="center">Analysis of Beer Hops</h1>
  <p align="center">
    4447 - Tools 1 - Fall 2021 - Final Project
    <br />
    Tomer Danon & Romith Challa
    <br />
    <br />
    <a href="https://github.com/rc-9/tools1_project">View Repo</a>
    ·
    <a href="https://github.com/rc-9/tools1_project/issues">Report Bug</a>
    ·
    <a href="https://github.com/rc-9/tools1_project/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prereqs">Prerequisite Installations</a></li>
        <li><a href="#repoclone">Repository Cloning</a></li>
        <li><a href="#envsetup">Environment Setup</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
      <ul>
        <li><a href="#scraper">Scraper</a></li>
        <li><a href="#cleaner">Cleaner</a></li>
        <li><a href="#eda">EDA</a></li>
        <li><a href="#classifier">Classifier</a></li>
        <li><a href="#analyer">Analyzer</a></li>
      </ul>
    </li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



## About The Project

Hops are primarily used as a bittering, flavoring, and stabilizing agent in beer. 
In recent years, hops have become the center of attention in the beer industry, as hop-forward beers have become one of the most popular styles of beer. 
Hops varieties are developed and grown in moderate climates around the world. 
Every branded hop variety has a unique flavor and aroma profile. 
This makes for an exciting and delicious reason to explore what flavor and aroma a hop can offer on its own, or together with other hops to bring waves and layers of flavor and aromas. 

The purpose of this project is to build a processed dataset to explore some definitive hop characteristics, draw initial insights into geographical relationships between hops, and lay the groundwork for further model-building in future studies. 
The first step was to compile a comprehensive dataset that consists of these characteristics, consisting of both numeric brew values, as well as an aroma profile for each hop.
This was achieved through scraping BeerMaverick's database of a diverse set of 300+ hops from around the world. 
This raw data was thoroughly processed for exploratory studies, and feature-engineered to create insightful visualizations & prepare for initial model-building.
Using a supervised extreme-gradient boosting algorithm, this preliminary model was built for a deeper look into classification techniques for beer hops.


<p align="right">(<a href="#top">back to top</a>)</p>



## Getting Started

Steps to download a local copy of the project and reproduce the findings are outlined below.

### Prerequisites

Python 3.X and a means of accessing iPython notebook files is assumed. Links below walk through the necessary steps to fulfill these prerequisites.

Windows:
<br/>
https://medium.com/@kswalawage/install-python-and-jupyter-notebook-to-windows-10-64-bit-66db782e1d02
<br/>
MacOS:
<br/>
https://docs.python-guide.org/starting/install3/osx/
<br/>
https://medium.com/@blessedmarcel1/how-to-install-jupyter-notebook-on-mac-using-homebrew-528c39fd530f

### Repository Cloning

1. Navigate to a directory to save the repo through a Terminal.
   ```
   cd c:\path\to\directory
   ```
2. Clone the repo
   ```
   git clone https://github.com/rc-9/tools1_project.git
   ```
   
### Environment Setup

1. Install virtual environment capability.
    ```
    pip install virtualenv
    ```
2. Navigate to directory of the cloned repo and create a virtual environment for the project.
    ``` 
    python -m venv c:\path\to\directory\venvname
    ```
3. Activate virtual environment for the project.
    ``` 
    .\venv\Scripts\activate
    ```
4. Install necessary modules from the provided requirements file.
    ``` 
    pip install -r requirements.txt
    ```
5. Launch Jupyter through virtual environment to view and execute codeblocks or run scripts directly in Terminal for outputs files.

<p align="right">(<a href="#top">back to top</a>)</p>


## Usage

This section outlines the order to execute iPython scripts to retrieve & clean the necessary data, generate visuals, perform analysis, and build a basic classification model.
<br/> <br/>

1. Execute ```step1_scraper.ipynb``` to collect the info from BeerMaverick's Hops Database.
This script is designed to take **40+ minutes** to fully execute and scrape all the necessary data. 
As the database contains over 300+ hops, each with individual webpages for detailed info, the scraper is set up with a wait-time to ensure the scraping can be fully completed without running into automatic IP blocks. 
**This step is optional and can be skipped to avoid the long run-time as the output ```raw_data.csv``` is already provided in the repository.**
<br/> <br/>
The raw data is stored in the ```raw_data``` directory consisting of the following ```csv``` files:
    - ```raw_hops_main.csv```: primary data file to be used for cleaning & analysis
    - ```raw_ref_aroma_types.csv```: reference document for metadata info on aroma types
    - ```raw_ref_brew_values.csv```: reference document for metadata info on brew values
    - ```raw_ref_hops_substitutions.csv```: reference document for metadata info on pre-determined hop substitutions
<br/> <br/> <br/>

2. Execute ```step2_cleaner.ipynb``` to wrangle and feature-engineer the raw data files from ```raw_data``` and store cleaned data into ```clean_data```.
<br/> <br/>
The ```clean_data``` directory consists of the following ```csv``` files:
    - ```cln_hops_brewvalues.csv```: processed numerical data for various brew values for each hop
    - ```cln_hops_profile.csv```: processed categorical & boolean data of country, purpose, aroma info for each hop
    - ```cln_ref_aroma_types.csv```: processed reference document for metadata info on aroma types
    - ```cln_ref_brew_values.csv```: processed reference document for metadata info on brew values
    - ```cln_ref_hops_substitutions.csv```: processed reference document for metadata info on pre-determined hop substitutions
<br/> <br/> <br/>

3. Execute ```step3_eda.ipynb``` which uses the processed data files from ```clean_data``` to perform exploratory analysis, generate insightful visualizations, and gain clarity for further study.
<br/> <br/>
The ```eda_visuals``` directory generated from execution will consist of the following ```png``` files:
    - ```.png```: 
    - ```.png```: 
    - ```.png```: 
    - ```.png```: 
    - ```.png```:
<br/> <br/> <br/>

4. Execute ```step4_classifier.ipynb``` to build a basic tree-based ensemble model using XG-Boost classification algorithm.
<br/> In this step, we attempt to classify geographical regions based on various hop characteristics. 
The processed data from ```clean_data``` undergoes further feature-engineering to prepare to be fed into a model that can carry out this task. This script is self-contained and will consist of the resulting confusion matrix from the model predictions.
<br/> <br/> <br/>

5. Execute ```step5_analyzer.ipynb``` to generate a compiled summary of analyses and explanatory visualizations that give insight into the hops characteristics.
The ```summary_visuals``` directory generated from execution will consist of the following ```png``` files:
    - ```.png```: 
    - ```.png```: 
    - ```.png```: 


<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

* Tomer Danon - [tomer.danon@du.edu](tomer.danon@du.edu)
* Romith Challa - [romith.challa@du.edu](romith.challa@du.edu)

<p align="right">(<a href="#top">back to top</a>)</p>


## Acknowledgments

* Data source: [https://beermaverick.com/hops/](https://beermaverick.com/hops/)
* Ritchie School of Engineering & Computer Science, University of Denver

<p align="right">(<a href="#top">back to top</a>)</p>





<!-- MARKDOWN LINKS & IMAGES -->
[contributors-shield]: https://img.shields.io/github/contributors/rc-9/tools1_project.svg?style=for-the-badge
[contributors-url]: https://github.com/rc-9/tools1_project/graphs/contributors
[issues-shield]: https://img.shields.io/github/issues/rc-9/tools1_project.svg?style=for-the-badge
[issues-url]: https://github.com/rc-9/tools1_project/issues















