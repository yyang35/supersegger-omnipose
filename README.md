# <p> <b>SUPERSEGGER-OMNIPOSE</b> </p>

Supersegger-Omnipose is the Supersegger MATLAB-based suite modified to work with improved Omnipose segmentation. Omnipose should be installed before running Supersegger-Omnipose.

Omnipose can be found [here](https://github.com/kevinjohncutler/omnipose/).



### Software Requirements

Supersegger-Omnipose uses the same MATLAB toolboxes as the original Supersegger:

- Curve Fitting Toolbox
- Deep Learning Toolbox (fka Neural Network Toolbox)
- Global Optimization Toolbox
- Image Processing Toolbox
- Parallel Computing Toolbox (not necessary)
- Statistics and Machine Learning Toolbox



### Software Documentation

The Github for Supersegger is [here](https://github.com/wiggins-lab/SuperSegger). For more detailed documentation, the website for Supersegger can be found [here](http://mtshasta.phys.washington.edu/website/SuperSegger.php). Supersegger-Omnipose uses the same MATLAB functions as the original Supersegger.

Omnipose options have been preselected to work directly with Supersegger, but if needed, further documentation can be found [here](https://cellpose.readthedocs.io/en/latest/command.html).

The following default Omnipose options can be modified depending on the desired usage: "--cluster --dist_thresh 1".
In addition, other Omnipose options can be added to possibly improve segmentation. 
However, Supersegger-Omnipose requires the following options following --omni: "--save_png --dir_above --in_folders"



### Installation Instructions

1. Install [MATLAB](https://www.mathworks.com/help/install/install-products.html), [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git), and [miniconda](https://docs.conda.io/en/latest/miniconda.html).
2. Install/clone Supersegger-Omnipose
```
git clone https://github.com/tlo-bot/supersegger-omnipose
```
3. Install/clone [Omnipose](https://github.com/kevinjohncutler/omnipose/) from github.
   - Find step-by-step instructions here.
   - Omnipose can also be installed through pip: `pip install omnipose`
   - Further installation instructions for Omnipose can be found [here](https://pypi.org/project/cellpose/).
3. Add supersegger-omnipose to MATLAB path, with its subfolders.


### Setting the Path

In order for Matlab to be able to find SuperSegger-Omnipose, the SuperSegger-Omnipose folder needs to be in your path*. In the Home tab, in the Environment section, click Set Path. The Set Path dialog box appears. Click 'add folder with subfolders' and add the SuperSegger-Omnipose folder. 

_*note that if the original Supersegger is already installed and on the MATLAB path, you should replace the paths of the original Supersegger folders & subfolders with the paths to the new Supersegger-Omnipose folders & subfolders._



### Running Supersegger-Omnipose

1. Put images (.tif) into a folder.
2. Convert image file names to Supersegger convention (in MATLAB with `superSeggerGui`, or `convertImageNames`; or manually with command line).
3. Run `superSeggerGui`, or configure and run `processExp`. Supersegger-Omnipose will begin aligning the images.
   - After aligning, Supersegger-Omnipose will pause for segmentation through Omnipose. The Omnipose command should be displayed on the MATLAB Command Window and also automatically copied to your clipboard.
4. Open a terminal and start Omnipose (ie `conda activate cellpose`)
5. Paste in the Omnipose command that was generated by MATLAB into the terminal. Wait for Omnipose to segment images and generate masks.
6. Once Omnipose has completed, continue running Supersegger by simply pressing the return/Enter key in the MATLAB Command Window.

### Troubleshooting & Known Issues
Coming soon: 
- Omnipose installation instructions (Windows, Linux & MacOS)
- Possible Supersegger-Omnipose errors










