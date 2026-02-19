# analysis of anscombe data 

## Goal 

Analyse data set and vidualise it, and see what we want to do next with it 

## Implementation 

- First, look at the data and generate descriptive statistics. 
- Second, create a Jupyter Light notebook in which you will generate plots.
- Propose the type of plots that you would like to generate.
- Save this proposal to the end of this file and let me look at it. 
- I will need to approve this plan and tell you to go ahead before we actually do anything. Please append the plan to the end of this file

---

## Descriptive Statistics

All four datasets share nearly identical summary statistics — this is the famous property of Anscombe's Quartet.

| Dataset | x mean | x std | y mean | y std | x-y correlation | Regression |
|---------|--------|-------|--------|-------|-----------------|------------|
| I       | 9.0    | 3.32  | 7.50   | 2.03  | 0.816           | y = 3.00 + 0.50x |
| II      | 9.0    | 3.32  | 7.50   | 2.03  | 0.816           | y = 3.00 + 0.50x |
| III     | 9.0    | 3.32  | 7.50   | 2.03  | 0.816           | y = 3.00 + 0.50x |
| IV      | 9.0    | 3.32  | 7.50   | 2.03  | 0.817           | y = 3.00 + 0.50x |

Notable structural differences (visible only in plots):
- **I**: Clean linear relationship with some scatter
- **II**: Curved (quadratic) relationship
- **III**: Linear relationship with one high-leverage outlier (x=13, y=12.74)
- **IV**: All x values are 8 except one outlier at x=19; y is essentially constant otherwise

---

## Proposed Plots

The notebook will contain a 2x2 grid of scatter plots, one per dataset, each with the shared regression line overlaid. This is the canonical visualization for Anscombe's Quartet and directly demonstrates why summary statistics alone are misleading.

**Plot 1 — 2x2 Scatter Grid with Regression Lines**
- Four subplots (I, II, III, IV) arranged in a 2x2 grid
- Each shows the raw (x, y) scatter points
- Each overlays the fitted regression line (y = 3.00 + 0.50x)
- Axes are scaled identically across all four panels for direct visual comparison
- Annotation showing mean x, mean y, and r for each panel

**Plot 2 — Residual Plots**
- Four subplots showing residuals (y − ŷ) vs x for each dataset
- Reveals the non-linearity in dataset II and the outlier structure in III and IV that the regression line masks

**Rationale:** Plot 1 is the classic illustration of the quartet's key lesson. Plot 2 deepens the analysis by showing what the regression line fails to capture, making it useful for understanding model diagnostics.
