# The SIGMA templates and atlases for the Wistar Rat Brain 10.5281/zenodo.10635532

The current document is a short description of the second version of the SIGMA resources for the Wistar rat brain. 
For a full description of the resources and the methodologies used to create them please consult the main publication [Barriere D.A. et al 2019].

The SIGMA resources are a set of standardized MRI compatible templates and atlases meant to support the analysis of multimodal MRI data of the rat brain. 
They were developped as part of the SIGMA project, a collaborative project between French (CEA and INSERM) and Portuguese (ICVS) institutions (FCT-ANR/NEU-OSD/0258/2012). 
They provide a unified and standardized framework for the analysis of multimodal rat brain imaging data, allowing the reporting of results within the coordinate system of the Paxinos-Watson atlas. 

In this second version, standardized MRI compatible templates have been built from the original acquired data (11.7 Tesla Bruker Scanner at Neuropsin center https://www.cea.fr/drf/joliot/en/Pages/research_entities/NeuroSpin.aspx) and emulated using the methods developed by Gabriel A. Devenyi (https://github.com/gdevenyi) and available here : 
https://github.com/CoBrALab/optimized_antsMultivariateTemplateConstruction. 
This pipeline is a re-implementation of the ANTs template construction pipeline requiring ANTs for the primary commands, and running on our cluster facilities using qbatch (https://islande.hub.inrae.fr/infrastructure).

Using this methodology we firstly, updated the previous SIGMA spaces (T2sw, T2w, T1w) previously generated using the DARTEL Methods implemented in SPM8 and normalized the whole head images instead of brain.

Secondly, we updated the probabilistic maps of the rat brain which are mandatory for the automatic segmentation of the rat brain and standardisation of morphometric analysis.
Namely, we created new maps of Grey Matter, White Matter, CSF, Skull and outbrain.
Those maps allow the use of SIGMA with the latter release of SPM12, a popular neuroimaging software dedicated to brain imaging analysis but also with ANTs, FSL and AFNI.
Additionnally, we revised the Grey Matter/White Matter segmentations since the limits of which (particularly at the thalamic level) were a matter to debate with some users in the previous version of SIGMA.

Thirdly, additionnal templates have been created using the optimized ANTs methodology to create from original unpublished data diffusion templates (B0, FA, etc.) at both ex-vivo and in-vivo resolutions.

Eventually, using the same strategy, we created a CT/18FDG reference space from data obtained previously [Barrière D.A. et al 2018] which has been normalized with the MRI ex-vivo SIGMA template allowing to the SIGMA resource to propose a multimodal space for CT/TEP/MRI normalisation.


## Organisation of the SIGMA resources
The SIGMA resources have been organized as four sections : anatomical Imaging, functional imaging, atlases and TEP/CT imaging

  ### Anatomical Imaging
  In this section a set of templates, priors and brain masks is available for ex-vivo and in-vivo data normalization
  #### Ex-vivo T2*-weighted
  T2*-weighted template + T2*-weighted map + associated probabilistics maps (GM, WM, CSF, Skull, outbrain) + brain mask.
  
  Spatial resolution 0.09x0.09x0.09mm.
  
      SIGMA_ExVivo_Anatomical_Brain_csf.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_gm.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_mask.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_out.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_skull.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_t2starmap.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_template.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_wm.nii.gz

  #### Ex-vivo diffusion
  B0 template + FA template + associated probabilistics maps (GM, WM, CSF, Skull, outbrain) + brain mask.
  
  Spatial resolution 0.25x0.25x0.25mm.
  
      SIGMA_ExVivo_Diffusion_Brain_b0.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_csf.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_fa.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_gm.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_mask.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_out.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_skull.nii.gz
      SIGMA_ExVivo_Diffusion_Brain_wm.nii.gz

  #### In-vivo T2-weighted
  T2-weighted template + associated probabilistics maps (GM, WM, CSF, Skull, outbrain) + brain mask.
  
  Spatial resolution 0.15x0.15x0.15mm.

      SIGMA_InVivo_Anatomical_Brain_csf.nii.gz
      SIGMA_InVivo_Anatomical_Brain_gm.nii.gz
      SIGMA_InVivo_Anatomical_Brain_mask.nii.gz
      SIGMA_InVivo_Anatomical_Brain_out.nii.gz
      SIGMA_InVivo_Anatomical_Brain_skull.nii.gz
      SIGMA_InVivo_Anatomical_Brain_template.nii.gz
      SIGMA_InVivo_Anatomical_Brain_wm.nii.gz

  #### In-vivo diffusion
  T2-weighted template + B0 template + FA template + ADC template + brain mask.
  
  Spatial resolution 0.375x0.375x0.375mm.

      SIGMA_InVivo_Diffusion_Brain_adc.nii.gz
      SIGMA_InVivo_Diffusion_Brain_b0.nii.gz
      SIGMA_InVivo_Diffusion_Brain_fa.nii.gz
      SIGMA_InVivo_Diffusion_Brain_mask.nii.gz
      SIGMA_InVivo_Diffusion_Brain_t2.nii.gz

  ### Functional Imaging
  T2-weighted template + associated probabilistics maps (GM, WM, CSF, Skull, outbrain) + brain mask.

  Spatial resolution 0.375x1x0.375mm.

      SIGMA_InVivo_Functional_Brain_csf.nii.gz
      SIGMA_InVivo_Functional_Brain_epi.nii.gz
      SIGMA_InVivo_Functional_Brain_gm.nii.gz
      SIGMA_InVivo_Functional_Brain_mask.nii.gz
      SIGMA_InVivo_Functional_Brain_t2.nii.gz
      SIGMA_InVivo_Functional_Brain_wm.nii.gz

  ### SIGMA Rat Brain Atlas Version 2.0 : Waxholm atlas Feat. SIGMA
  In this second version of the SIGMA resources we deliver a new SIGMA brain atlas obtained by the normalization of the Waxholm space published by Kleven, H. et al. Nat Methods (2023, https://doi.org/10.1038/s41592-023-02034-3).
  The Waxholm rat brain atlas is currently the best numerical 3D atlas of the rat brain.
  In accordance with authors of this paper we are authorized to modify and embed the WHS atlas within the SIGMA environement to standardize the identification of brain territories.
  We provide a normalized version the WHS for both ex-vivo and in-vivo of the anatomical SIGMA templates. Finally, we offer linear and non-linear transformations to enable your data to commute between the SIGMA and WHS ex-vivo environments using ANTs commands.
  
  #### Ex-vivo atlas
  WHS rat brain atlas normalized in ex-vivo T2*-weighted SIGMA template + List of 222 labels created in ITKSnap Format + linear and non-linear transformations for SIGMA-WHS journeys (WHS-to-SIGMA_Transformations folder).

  Spatial resolution 0.09x0.09x0.09mm.

      SIGMA_ExVivo_Anatomical_Brain_Atlas.nii.gz
      SIGMA_ExVivo_Anatomical_Brain_Atlas.txt
      ./WHS-to-SIGMA_Transformations/reference_SIGMA.nii.gz
      ./WHS-to-SIGMA_Transformations/reference_WHS.nii.gz
      ./WHS-to-SIGMA_Transformations/WHS-in-SIGMA_transform_01_InverseWarp.nii.gz
      ./WHS-to-SIGMA_Transformations/WHS-in-SIGMA_transform_01_Warp.nii.gz
      ./WHS-to-SIGMA_Transformations/WHS-in-SIGMA_transform_02_GenericAffine.mat
      ./WHS-to-SIGMA_Transformations/WHS-in-SIGMA_transform_03_GenericAffine.mat
      ./WHS-to-SIGMA_Transformations/WHS_SD_rat_atlas_v4.nii.gz
      ./WHS-to-SIGMA_Transformations/WHS-to-SIGMA_byANTS.txt

  #### In-vivo atlas
WHS rat brain atlas normalized in in-vivo T2 SIGMA anatomical template + List of 222 labels created in ITKSnap Format.

Spatial resolution 0.15x0.15x0.15mm.

      SIGMA_InVivo_Anatomical_Brain_Atlas.nii.gz
      SIGMA_InVivo_Anatomical_Brain_Atlas.txt

  #### SIGMA brain meshes
Rat brain mesh created using BrainNet viewers commands in matlab (https://www.nitrc.org/projects/bnv/).
  
  Spatial resolution 0.09x0.09x0.09mm.

      SIGMA_Anatomical_Brain_Atlas_mesh.nv

  #### SIGMA functional atlas
In the original publication of the SIGMA resources, we developed a functional atlas for the rat brain, using a group ICA analysis validated through a RAICAR approach. From this analysis, we identified 59 bilateral ROIs covering cortical, sub-cortical and brainstem structures that are functionally distinct. Despite having been derived from purely functional data, this atlas broadly, if not precisely, correlates with the general anatomical boundaries and many are associated with specific anatomical structures. A primary motivation for the creation of this atlas is derived from the need to perform brain segmentations which is optimized for functional MRI analysis, since the signal sources do not necessarily match typical anatomical boundaries. A similar requirement has been identified by those performing human studies, resulting in efforts to generate more diverse, multi-modal atlases.

SIGMA rat brain functional atlas normalized in in-vivo T2 SIGMA functional template + List of 59 labels created in ITKSnap Format.

  Spatial resolution 0.375x1x0.375mm.

      SIGMA_Functional_Brain_Atlas_Labels.txt
      SIGMA_Functional_Brain_Atlas_ListOfStructures.csv
      SIGMA_InVivo_Functional_Brain_Atlas.nii.gz

  #### SIGMA CT/TEP template
In this version of the SIGMA resources we included a CT/TEP template built from the data that previously published (Barriere D.A. et al 2018 , Sci Rep. 2018 Jan 11;8(1):424. doi: 10.1038/s41598-017-18896-5) and acquired on a Triumph™ PET/CT dual modality imaging platform (Gamma Medica, Inc., Northridge, CA, USA), consisting of a LabPET™ avalanche photodiode-based digital PET scanner with a 7.5 cm axial field-of-view capable of achieving an isotropic spatial resolution. A caudal injection of approximately 30 MBq of [18F]-FDG was applied followed by a static acquisition to evaluate [18F]-FDG uptake within brain. CT images were acquired from the high-resolution X-ray computed tomography (CT) modality. Images were reconstructed using the Triumph™ PET/CT software.  using the following parameters: 20 iterations, span of 63, field of view of 80 mm with a final matrix resolution of 160 × 160 × 128 and a voxel size of 0.5 × 0.5 × 0.597 mm. Brain dynamic [18F]-FDG images were reconstructed using the same protocol but we generated 32 frames (10 for 5 s, 7 for 10 s, 6 for 30 sec, 6 for 120 s, 2 for 240 s and 1 for 300 s). 
[18F]-FDG images were reconstructed using 3-D MLEM algorithm providing 0.5 × 0.5 × 0.597 mm images. CT scans were reconstructed using the standard FBP kernel analytical reconstruction algorithms, providing an isotropic image of 512 slices with a final resolution of 0.165 µm isotropic. Both [18F]-FDG and CT data were spatially normalized to the SIGMA ex-vivo template using the previously described methods.

Spatial resolution 0.09x0.09x0.09mm.

      SIGMA_InVivo_18FDG_Brain_template.nii.gz
      SIGMA_InVivo_CT_Brain_template.nii.gz

## Important Note
SIGMA ressources are provided at the scanner resolution and are oriented in anterior commisure/posterior commisure axis. Center of the images have been set at the anterior commisure level (Bregma 0 mm). Nevertheless, users are invited to increase the resolution of the current images for using in SPM or FSL for accurate coregistration and normalization steps (we recommand x10 increasing). No manipulation of image resolution are required with ANTs. Not tested with AFNI.

For any questions regarding the SIGMA ressource, please email the SIGMA Team (sigma.preclinical.resources@gmail.com) or Email directly David A. Barrière (david.barriere@cnrs.fr).

# REFERENCES
Barrière, D.A. et al. The SIGMA rat brain templates and atlases for multimodal MRI data analysis and visualization. Nat Commun 10, 5699 (2019). https://doi.org/10.1038/s41467-019-13575-7

Kleven, H. et al. Waxholm Space atlas of the rat brain: a 3D atlas supporting data analysis and integration. Nat Methods 20, 1822–1829 (2023). https://doi.org/10.1038/s41592-023-02034-3

Barrière, D.A. et al. Combination of high-fat/high-fructose diet and low-dose streptozotocin to model long-term type-2 diabetes complications. Sci Rep. 2018 Jan 11;8(1):424. doi: 10.1038/s41598-017-18896-5. PMID: 29323186; PMCID: PMC5765114.

# RELATED WORKS USING THE SIGMA RESSOURCES
Grandjean J. et al. A consensus protocol for functional connectivity analysis in the rat brain. Nat Neurosci. 2023 Apr;26(4):673-681. doi: 10.1038/s41593-023-01286-8. Epub 2023 Mar 27. Erratum in: Nat Neurosci. 2023 Jun;26(6):1127-1128. PMID: 36973511; PMCID: PMC10493189.

Vidal B. et al. Inter-subject registration and application of the SIGMA rat brain atlas for regional labeling in functional ultrasound imaging. J Neurosci Methods. 2021 May 1;355:109139. doi: 10.1016/j.jneumeth.2021.109139. Epub 2021 Mar 16. PMID: 33741345.

Barrière D.A. et al. Paracetamol is a centrally acting analgesic using mechanisms located in the periaqueductal grey. Br J Pharmacol. 2020 Apr;177(8):1773-1792. doi: 10.1111/bph.14934. Epub 2020 Jan 22. PMID: 31734950; PMCID: PMC7070177

Barrière D.A. et al. Structural and functional alterations in the retrosplenial cortex following neuropathic pain. Pain. 2019 Oct;160(10):2241-2254. doi: 10.1097/j.pain.0000000000001610. PMID: 31145220.

Magalhães, R. et al Resting-State Functional MR Imaging and Spectroscopy Study of the Dorsal Hippocampus in the Chronic Unpredictable Stress Rat Model. J Neurosci. 2019 May 8;39(19):3640-3650. doi: 10.1523/JNEUROSCI.2192-18.2019. Epub 2019 Feb 25. PMID: 30804096; PMCID: PMC6510342.

Magalhães, R. et al The dynamics of stress: a longitudinal MRI study of rat brain structure and connectome. Mol Psychiatry. 2018 Oct;23(10):1998-2006. doi: 10.1038/mp.2017.244. Epub 2017 Dec 5. PMID: 29203852.
