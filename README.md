# silicoDCIS_mechanics

**Project Title:** Interplay of cellular and extracellular matrix interactions leading to DCIS microinvasions: a mechanical perspective.

**Description:** This set of codes simulates tumor growth and microinvasions in ductal carcinoma in situ (DCIS). Microinvasions are a cohort of cancer cells that break the integrity of the mammary duct and invade the stroma, constituting the first physical step toward cancer metastasis. All codes are generated in MATLAB.

**Dependencies:** The R2023b version of MATLAB on a Mac computer was used for all testing.
Installation: This code does not need installation.

**Authors:** Ana Forero Pinto, Mehdi Damaghi, and Katarzyna Rejniak.

**Version 0.1:** Initial release.

**License:** This project is licensed under the GNU General Public License v3.0. 

**Executing the program:** download the MATLAB files of interest in each of the folders and run. Be careful to include the folder where the initial conditions data is contained (Initconditions folder). 

**Folders and files:**

**- ParameterEstimation:** Contains the code used to estimate the repulsive stiffness of epithelial cells (ECs).

**- Initconditions:** Generation of initial conditions for tumor growth. This folder contains two codes, stabilize_cells.m and stabilize_BMaftercells.m.

In stabilize_cells.m the two layers of epithelial cells (ECs) and myoepithelial cells (MECs) are placed in a circle to generate the mammary duct cross-section, and their forces are then stabilized. The folder output “cellsPositions” contains the initial positions of epithelial and myoepithelial cells that will later be used in the next code: “stabilize_BMaftercells.m”.

In stabilize_BMaftercells.m, we used the input data in the folder “cellsPositions” to place the initial ECs and MECs layers and then create the basement membrane (BM). Later, we stabilized the interaction forces of the ductal structure components and integrated the extracellular matrix (ECM). The output folder “data” contains all the information of the normal mammary duct structure such as: Cells, BM and ECM positions; ECs ages and maturation ages; ECs and MECs radii; ECM density values; and force-related resting lengths.

**- silicoDCIS_Mechanics.m:** This main code is used to generate the images shown in our publication “Interplay of cellular and extracellular matrix interactions leading to DCIS microinvasions: a mechanical perspective”. Please refer to the “Examples” folder as a guide to using this code.

**- Examples:** containing three folders/examples:

1_SupFig_ductGrowth: this folder contains two examples shown in the supplemental figure of the publication related to tumor growth. 

The first code “silicoDCIS_Mechanics_100kBM.m” generates the folder “output_100kbm” containing all the relevant information of the DCIS dynamics over time. The final time output is then used as initial conditions for the upcoming examples in folders “2_Fig5” and “3_Fig10”. 

The second code, “silicoDCIS_Mechanics_sigma0.m”, shows which parameters to change to generate supplemental figure Fig. S2, panel where σ^BM=0 and κ^BM=10κ_r^EpiEpi. If you would like to generate its outputs, please run this code; otherwise, follow the instructions in its header to correctly modify the parameters, and run the code to generate outputs.

To render images, run the code “renderingImages.m” inside the folder “rendering_images”. This code automatically uses the MATLAB package curvvec. If you would like to generate only one image, please follow the instructions in the header of the same code.

**2_Fig5:** This folder contains two examples shown in the supplemental figures Fig. 5a and Fig. 5d of the publication. 
The first code “silicoDCIS_Mechanics_BMnMECn” shows which parameters to change to generate Fig. 5a. If you would like to generate its outputs, please run this code; otherwise, follow the instructions in its header to correctly modify the parameters for figures Fig. 5b,c.

The second code “silicoDCIS_Mechanics_BMyMECy” generates the folder “output_BMyMECy” containing all the relevant information for the generation of DCIS microinvasions over time. The final time output is then used as initial conditions for the examples in folders “3_Fig10”.

**3_Fig10:** This folder contains the code that generates outputs of the three different force magnitude cases shown in Fig.10 of the publication. These are then used to create the supplemental video associated with this figure.

To create the supplemental video, run the MATLAB file “meanBMtensionAndECMdensity4MOVIE.m” within the “Video” folder. It will use the packages curvvec and plotfigswithBMbreakFUN and generate a folder “MovieFigs” with all the video frames.

