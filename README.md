# MagnetXplorers

MagnetXplorers is using a simplified version of the SpinSight MRI simulator.

For informations about Spinsight, please contact his author:
Johan Berglund, Ph.D.
Uppsala University Hospital,
Uppsala, Sweden
johan.berglund@akademiska.se

---
Install through Anaconda:

1. Install Anaconda through the website.
2. Create an environment with Python 3.1
3. Open the environment in the Anaconda prompt
4. Then type "pip install spinsight"
5. In the Anaconda prompt check that everything is installed by typing "pip show spinsight". If nothing or an error comes back then something went wrong with the installation.
6. In case you receive a text message back, check for the "location" folder. Copy and paste this location in your "File explorer".
7. Then click on the "spinsight" folder and replace the content of the folder "spinsight" that you downloaded from here on Github. You are done installing the interface.
8. IMPORTANT: In order to load the "digital phantom" of Arkynox (see B. of the screenshot at the end of this page), you need to change the "X" line 2062 of the "main_magnetXplorers.py" file in order to indicate the location of the "Arkynox_2x_clean_center.svg" file.
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
* Text characters must be avoided if possible. If not, they may raise an error from the code. If it is the case, try drawing the letters or numbers you want to include. 

We recommend Inkscape for the phantom construction, it has been used for the development of Arkynox. However, any software generating an svg file will work.

Dependencies
------------
See [pyproject.toml](./pyproject.toml) under heading **[tool.poetry.dependencies]**. 

License
-------
SpinSight is distributed under the terms of the GNU General Public License. See [LICENSE.md](./LICENSE.md).

Contact Information
-------------------
For MagnetXplorers <br>
Roberta Frass-Kriegl, Ph.D. <br>
Medical University of Vienna <br>
Vienna, Austria <br>
roberta.frass@meduniwien.ac.at
<img width="2507" height="3333" alt="Screenshot_Simulation" src="https://github.com/user-attachments/assets/4f813cc9-fef7-4a3c-ba5b-2c46b31c9453" />

---
Copyright © 2021–2025 Johan Berglund.
