## Introduction
This is how I installed PyBioMed with RDKit on my **Windows**. If you use other operation system this won't work for you!

## Installation
- Install [Python](https://www.python.org/downloads/release/python-3913).
    - Packages are installed by **pip**. Check commands on relative websites if you use other package managers.
    - Download and run Windows installer (select **"install pip"**).
 
- Install necessary packages 
    - Install Numpy with command: **"pip install numpy"**.
    - Install [RDKit](https://www.rdkit.org/) with command: **"pip install rdkit"**.
    - Install [Pybel](http://openbabel.org/docs/current/UseTheLibrary/PythonInstall.html) with command: **"pip install pybel"**.
    - Install wheel with command: **"pip install wheel"**.

-  Install PyBioMed ([Github link](https://github.com/gadsbyfly/PyBioMed)).
    - Download [PyBioMed](https://codeload.github.com/gadsbyfly/PyBioMed/zip/refs/heads/master) file.
    - [Locate your Python file loation](https://datatofish.com/locate-python-windows/#:~:text=Manually%20Locate%20Where%20Python%20is%20Installed&text=Type%20'Python'%20in%20the%20Windows,Click%20on%20%E2%80%9COpen%20File%20Location%E2%80%9C)
    - Install PyBioMed package
        - Locate package file location ("/Lib/site-packages")
        - Extract PyBioMed file "PyBioMed-master.zip" to here.
        - cd to this location in terminal and type "**python setup.py install**".

- Adjustment in
    - The original kappa package is not working due to rdkit update. New update from contributor from GitHub.
    Related links:
        - https://github.com/gadsbyfly/PyBioMed/pull/16
        - https://github.com/gadsbyfly/PyBioMed/pull/16/commits/- 263429e5ffa2ac7bf32ccb6fac969a12ce6cf637 
        - https://github.com/gadsbyfly/PyBioMed/blob/263429e5ffa2ac7bf32ccb6fac969a12ce6cf637/PyBioMed/PyMolecule/kappa.py


    - Function OnlyHeavy() is not working so change from "mol.GetNumAtom(onlyHeave=1)" to "mol.GetNumHeavyAtoms()" in "*PyMolecule/molproperty.py*" and "*PyMolecule/constitution.py*".
