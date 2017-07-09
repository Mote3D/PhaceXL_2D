## PhaceXL 2D

PhaceXL_2D is a script for the generation of finite-thickness interface elements for 2D polycrystal microstructure modelling. PhaceXL_2D parses a 2D polycrystal microstructure mesh file generated using the [Neper](http://neper.sourceforge.net/) software package and modified using the [Phon](http://dx.doi.org/10.5281/zenodo.16711) cohesive element generator and shrinks the existing grains by a predefined factor to create finite-thickness interface elements at the grain boundaries. PhaceXL_2D retains mesh periodicity at the domain boundary. The resulting mesh is exported in a format readable by Abaqus&#8482; software and can be used for finite-element analysis.

To generate a 2D polycrystal microstructure mesh with finite-thickness interface elements, the following steps 
have to be followed:

1. Generate a 2D polycrystal microstructure mesh using [Neper](http://neper.sourceforge.net/).
2. Export the polycrystal mesh as well as the coordinates of the grain centroids.
3. Use [Phon](http://dx.doi.org/10.5281/zenodo.16711) to insert zero-thickness cohesive elements at the grain boundaries.
4. Parse both files in PhaceXL_2D to generate finite-thickness interface elements at the grain boundaries.
5. Run finite-element analysis.


#### How to use the script:

Run phaceXL_2D using the command '*phaceXL_2D.py -i INPUTFILENAME -c CENTROIDFILENAME -p MPER -s SFACTOR*' from the command line. The following input parameters have to be specified:

 *INPUTFILENAME*: :::   name of the file containing the polycrystal microstructure mesh and the cohesive elements generated by  
                     [Neper](http://neper.sourceforge.net/) and [Phon](http://dx.doi.org/10.5281/zenodo.16711),  
 *CENTROIDFILENAME*: name of the file containing the coordinates of the grain centroids,  
 *MPER*:             indication whether the microstructure mesh is periodic ("y") or (by default) non-periodic ("n"),  
 *SFACTOR*:          factor controlling the amount of shrinkage for each grain.  


PhaceXL_2D has been tested with [Python](http://www.python.org/downloads/) 2.6.5 and [NumPy](http://www.scipy.org/scipylib/download.html) 1.3.0. PhaceXL_2D is licensed under the [GNU General Public License](LICENSE.txt).
