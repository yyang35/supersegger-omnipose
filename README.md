# <p> <b>SUPERSEGGER-OMNIPOSE (SuperSegger 2)</b> </p>

![Phase image, old SuperSegger segmentation, new SuperSegger 2 segmentation.](/assets/githubfig2.png)


Supersegger-Omnipose is the Supersegger MATLAB-based suite modified to work with improved Omnipose segmentation. Omnipose should be installed before running Supersegger-Omnipose.

More information about Omnipose can be found at the [Github](https://github.com/kevinjohncutler/omnipose/) and [documentation page](https://omnipose.readthedocs.io/).


---
### Software Requirements

Supersegger-Omnipose uses the same MATLAB toolboxes as the original Supersegger:

- Curve Fitting Toolbox
- Deep Learning Toolbox (fka Neural Network Toolbox)
- Global Optimization Toolbox
- Image Processing Toolbox
- Parallel Computing Toolbox (not necessary)
- Statistics and Machine Learning Toolbox


---
### Software Documentation

#### SuperSegger
The Github for the original Supersegger is [here](https://github.com/wiggins-lab/SuperSegger). For more detailed documentation, the website for Supersegger can be found [here](http://mtshasta.phys.washington.edu/website/SuperSegger.php), the [wiki](https://github.com/wiggins-lab/SuperSegger/wiki), and documentation on functions found [here](http://mtshasta.phys.washington.edu/website/superSegger/). Supersegger-Omnipose uses the same MATLAB functions as the original Supersegger.

[Quick-start guide for new users](../main/docs/quick_start_guide.md)

#### Omnipose
[Omnipose](https://omnipose.readthedocs.io/) options have been preselected to work directly with Supersegger-Omnipose, but if needed, further documentation can be found by running `python -m omnipose --help` in the omnipose environment. Recommended options can also be found on the [documentation page](https://omnipose.readthedocs.io/command.html). 

> ##### Segmentation Options: When running the Omnipose command in conda, the following default Omnipose options can be modified depending on the desired usage: "--cluster --mask_threshold 1 --flow_threshold 0 --diameter 30". 
> 
> --cluster: DBscan clustering, reduces oversegmentation of thin features [can remove option]
> 
> --mask_threshold: mask threshold [0 default, decrease to find more and larger masks]
> 
> --flow_threshold: flow error threshold [0.4 default, 0 to turn off]
> 
> --diameter: approximate diameter of cell in pixels (for rod-shape, this is the length of the short axis) [30 default, 0 to have omnipose estimate for each image]
> 
> Mask and flow threshold numbers can be tested quickly with the [Omnipose GUI](https://omnipose.readthedocs.io/gui.html) (`python -m omnipose`). In addition, other Omnipose options can be added to possibly improve segmentation. 
> 
> ##### Training Models: Other models can be used as well instead of the default "bact_phase_omni".
> 
> ##### Note that the options before "--omni" should not be changed when working with Supersegger-Omnipose.


---
### Installation Instructions

1. Install [MATLAB](https://www.mathworks.com/help/install/install-products.html) and [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
2. Cd to desired folder and clone Supersegger-Omnipose with git
```
git clone https://github.com/tlo-bot/supersegger-omnipose.git
```
3. Add supersegger-omnipose to MATLAB path, with its subfolders (see "Setting the Path").
4. Install [Omnipose](https://github.com/kevinjohncutler/omnipose/)
   - Find step-by-step instructions [here](../main/docs/install_omnipose.md).
   - Further advanced installation instructions for Omnipose can be found [here](https://pypi.org/project/cellpose/).
   - GPU usage is discussed [here](https://omnipose.readthedocs.io/installation.html#gpu-support). The Supersegger-Omnipose command defaults to using CPU only.


---
### Setting the Path

In order for Matlab to be able to find SuperSegger-Omnipose, the SuperSegger-Omnipose folder needs to be in your path*. In the Home tab, in the Environment section, click Set Path. The Set Path dialog box appears. Click 'add folder with subfolders' and add the SuperSegger-Omnipose folder. 

>*note that if the original Supersegger is already installed and on the MATLAB path, you should replace the paths of the original Supersegger folders & subfolders with the paths to the new Supersegger-Omnipose folders & subfolders.


---
### Running Supersegger-Omnipose (GUI)

1. Put images (.tif) into a folder.
2. Convert image file names to Supersegger convention (in MATLAB with `superSeggerGui`, or `convertImageNames`; or manually with command line).
3. Run `superSeggerGui`, or configure and run `processExp`. Supersegger-Omnipose will begin aligning the images.
   - After aligning, Supersegger-Omnipose will pause for segmentation through Omnipose. The Omnipose command should be displayed on the MATLAB Command Window and also automatically copied to your clipboard.
4. Open terminal/Anaconda Prompt and start Omnipose (ie `conda activate omnipose`)
   - Note that you should see the conda environment change from "(base)" to "(omnipose)"
5. Paste in the Omnipose command that was generated by MATLAB into the terminal. Wait for Omnipose to segment images and generate masks.
   -Can also change the command options in this step, if needed.
6. Once Omnipose has completed, continue running Supersegger by pressing the return/Enter key in the MATLAB Command Window.


---
### Running Supersegger-Omnipose (Command Line)

1. Put images (.tif) into a folder.
2. Convert image file names to Supersegger convention.
3. Configure `processExp` file.
4. In terminal, run `matlab -nodesktop -noFigureWindows -nosplash -r “processExp(‘dir’)”`
5. Open another terminal, navigate to folder with Omnipose, and start Omnipose (ie `conda activate omnipose`)
6. Once images are aligned in MATLAB terminal, run Omnipose command. Wait for Omnipose to segment images and generate masks.
7. Once Omnipose has completed, continue running Supersegger by pressing the return/Enter key in the MATLAB terminal.


---
### Running Supersegger-Omnipose and Omnipose directly from MATLAB 


Only supported when using `processExp`. Specify autoomni=1 input for processExp (ie `processExp('dirname',1)`). Disabled by default.
See documentation for setup linked below.


---
### Troubleshooting & Known Issues

- [Omnipose installation instructions (Windows, Linux & MacOS)](../main/docs/install_omnipose.md)
- [Possible Supersegger-Omnipose errors](../main/docs/so_errors.md)
- [Running Omnipose directly from MATLAB for Windows (verified)](../main/docs/omni_in_matlab_windows.md)
- [Running Omnipose directly from MATLAB for Linux (verified) & MacOS](../main/docs/omni_in_matlab_unix.md)












