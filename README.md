SpinSight MRI simulator
===
SpinSight is an MRI simulator written in Python and created for educational puposes. It jointly visualizes the imaging parameters, the MRI pulse sequence, the k-space data matrix, and the MR image. These are updated in near real-time when the user changes parameters. The simulator is run as a web browser dashboard. The data is simulated from computational 2D phantoms in vector graphics format (SVG).

Running the Simulator
---
Install using pip: 
```
pip install spinsight
```
Then run as a command line tool
```
spinsight
```
This serves SpinSight on the local host, so that the simulator can be run by navigating to [localhost](http://localhost) in the web browser. The same command line tool can be used to deploy the simulator on a local network, or on a web server (run `spinsight -h` for help). Be aware that several minutes are required upon loading a phantom for the first time.

# MagnetXplorer

MagnetXplorer is using a simplified version of the SpinSight MRI simulator.

---
Install through Anaconda:

1. Install Anaconda through the website.
2. Create an environment with Python 3.1
3. Open the environment in the Anaconda prompt
4. Then type "pip install spinsight"
5. In the Anaconda prompt check that everything is installed by typing "pip show spinsight". If nothing or an error comes back then something went wrong with the installation.
6. In case you receive a text message back, check for the "location" folder. Copy and paste this location in your "File explorer".
7. Then click on the "spinsight" folder and replace the content of the folder "spinsight" that you downloaded from here on Github. You are done installing the interface.

---
How to run the MagnetXplorer interface:
1. Open the Anaconda prompt.
2. Open the environment in which you installed spinsight.
3. Type "spinsight"
4. Click on the "localhost" link that will appear in the prompt. This should open a tab in your default browser with the MagnetXplorer interface. It will take some minutes the very first time as the code has to generate and save specific files for the phantoms.

Phantom construction
--------------------
To create a new phantom, add a directory with the phantom name under [spinsight/phantoms](./spinsight/phantoms). This directory shall contain specifications in an `.svg` file with the same name (see [brain.svg](./spinsight/phantoms/brain/brain.svg) for reference). The specified `.svg` file must meet the following specifications:
* All paths must be closed
* All paths must have a fill color matching a hexcolor defined in the `TISSUES` dict in (./spinsight/constants.py) (this defines the tissue).
* Only polygons are supported (not Bézier curves etc)
* Text characters must be avoided if possible. If not, they may raise an error from the code. 

We recommend Inkscape for the phantom construction, it has been used for the development of Arkynox. However, any software generating an svg file will work.

Dependencies
------------
See [pyproject.toml](./pyproject.toml) under heading **[tool.poetry.dependencies]**. 

License
-------
SpinSight is distributed under the terms of the GNU General Public License. See [LICENSE.md](./LICENSE.md).

Contact Information
-------------------
For Spinsight
Johan Berglund, Ph.D.  
Uppsala University Hospital,  
Uppsala, Sweden  
johan.berglund@akademiska.se

![](spinsight.png) 

For MagnetXplorer
Roberta Frass-Kriegl, Ph.D.
Medical University of Vienna
Vienna, Austria
roberta.frass@meduniwien.ac.at

---
Copyright © 2021–2025 Johan Berglund.
