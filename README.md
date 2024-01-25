extractionQA script for PFS pipe2d

Quality assurance of the extraction of 1D spectrum. The script makes a residual image (calexp - model image constructed from extracted spectrum),  evaluate the extraction quality, and measure the offset (center positions and widths) between the profiles in the calexp image and those in the constructed image.

Input data
- pfsConfig
- detectorMap
- fiberProfiles
- pfsArm
- calexp

Output data
- Summary plots : `extQA_stats_{:06}-{}{}.pdf`
-- The results of the residual analysis of extraction are plotted.
- Detail plots : `extQA_image_{:06}-{}{}.pdf`
-- The calexp, residual, and chi images and the comparison of the calexp profile and fiberProfiles are plotted for some fibers with bad extraction quality.
- pickle data : `extQA_image_{:06}-{}{}.pickle`
-- The statistics of the residual analysis are stored in the dict format.

Parameters
- fixWidth = Field(dtype=bool, default=False, doc="Fix the widths during Gaussian fitting")
- rowNum = Field(dtype=int, default=200, doc="Number of rows picked up for profile analysis")
- thresError = Field(dtype=float, default=0.1, doc="Threshold of the fitting error")
- thresChi = Field(dtype=float, default=1.5, doc="Threshold for chi standard deviation")
- fiberWidth = Field(dtype=int, default=3, doc="Half width of a fiber region (pix)")
- fitWidth = Field(dtype=int, default=3, doc="Half width  of a fitting region (pix)")
- plotWidth = Field(dtype=int, default=15, doc="Half width  of plot (pix)")
- plotFiberNum = Field(dtype=int, default=20, doc="Maximum fiber number of detailed plots")
