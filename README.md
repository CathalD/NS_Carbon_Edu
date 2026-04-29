# Large-Area Carbon Sampling


▶ **[Open Sampling Tool](https://ee-cathalpdoherty2.projects.earthengine.app/view/stratification-sampling-tool)** &nbsp;·&nbsp; **[View Source Code](https://github.com/CathalD/NS_Carbon_Edu.git)**

Field guidance for carbon stock estimation across large project areas

---

## Contents

1. [Why your sample size looks too small](#why-your-sample-size-looks-too-small)
2. [Option 1 — Divide your project area](#option-1--divide-your-project-area-into-smaller-sub-units)
3. [Option 2 — Stratification with geospatial tools](#option-2--stratification-with-geospatial-tools)
4. [Option 3 — Remote sensing-based methods](#option-3--remote-sensing-based-methods)

---

Why your sample size looks too small
To start: you did nothing wrong. The standard sample size formula was designed for small, relatively uniform plots. When applied to a landscape of thousands of hectares, it hits a statistical ceiling — not because your area is well-sampled, but because the formula assumes the entire area is homogeneous.

[!NOTE]
The core assumption that breaks down
The formula treats your entire project area as a single, internally consistent population. A large landscape spanning multiple ecosystem types, soil depths, and drainage classes will have far more internal variability than the model accounts for — and that variability is exactly what drives sample size.

As area increases, the formula approaches a fixed ceiling determined by variance and your precision targets — not by area. For a homogeneous area this is statistically correct. For a large, ecologically complex landscape it systematically underestimates how many samples you need.
<svg viewBox="0 0 760 260" xmlns="http://www.w3.org/2000/svg" style="width:100%;max-width:760px;display:block;margin:20px 0;">
  <!-- axes -->
  <line x1="75" y1="28"  x2="75"  y2="220" stroke="#d0d7de" stroke-width="1"/>
  <line x1="73" y1="220" x2="652" y2="220" stroke="#d0d7de" stroke-width="1"/>
  <!-- ceiling reference -->
  <line x1="75" y1="72" x2="648" y2="72" stroke="#ccc" stroke-width="1" stroke-dasharray="4,3"/>
  <text x="651" y="76" font-size="10" fill="#bbb" font-family="system-ui,sans-serif">ceiling</text>
  <!-- standard formula (black) — transformed from original, asymptotes at ceiling -->
<path d="M 75,216 C 123,167 200,101 295,79 C 382,68 458,67 650,66"
     stroke="#1a1a1a" stroke-width="2" fill="none"/>
  <!-- option 2: stratification tool (green dashed)
       Tracks standard formula for small areas, then rises beyond ceiling.
       Shape reflects n ∝ [1 + log10(area/1000)]² — concave-up on the log x-axis. -->
<path d="M 75,216 C 123,167 200,101 295,79 C 368,69 425,63 472,56 C 514,49 562,44 618,41 C 636,40 648,40 650,39"
     stroke="#2e7d32" stroke-width="1.8" fill="none" stroke-dasharray="8,4"/>
  <!-- option 1: divide into sub-units (blue)
       Each sub-unit ~31 plots; total grows linearly with area.
       Linear-in-area on a log x-axis = accelerating curve; exits chart top ~25,000 ha. -->
<path d="M 75,216 C 123,200 188,168 252,136 C 294,114 322,92 346,68 C 358,56 368,45 376,36"
     stroke="#1565C0" stroke-width="1.8" fill="none"/>
  <!-- dashed continuation and arrowhead -->
<path d="M 376,36 C 382,29 390,22 400,17"
     stroke="#1565C0" stroke-width="1.2" fill="none" stroke-dasharray="3,2"/>
<polygon points="401,14 396,21 406,20" fill="#1565C0"/>
<text x="409" y="19" font-size="9" fill="#1565C0" font-family="system-ui,sans-serif" font-style="italic">linear growth continues</text>
  <!-- y-axis label — rotated, positioned clear of axis -->
<text font-size="11" fill="#999" font-family="system-ui,sans-serif" text-anchor="middle"
     transform="translate(17,126) rotate(-90)">Sample size (n)</text>
  <!-- x-axis label -->
<text x="362" y="248" font-size="11" fill="#999" text-anchor="middle"
     font-family="system-ui,sans-serif">Project area</text>
  <!-- x-axis ticks and labels -->
  <line x1="147" y1="220" x2="147" y2="226" stroke="#ccc" stroke-width="1"/>
  <line x1="300" y1="220" x2="300" y2="226" stroke="#ccc" stroke-width="1"/>
  <line x1="478" y1="220" x2="478" y2="226" stroke="#ccc" stroke-width="1"/>
  <text x="147" y="237" font-size="10" fill="#bbb" text-anchor="middle" font-family="system-ui,sans-serif">500 ha</text>
  <text x="300" y="237" font-size="10" fill="#bbb" text-anchor="middle" font-family="system-ui,sans-serif">10,000 ha</text>
  <text x="478" y="237" font-size="10" fill="#bbb" text-anchor="middle" font-family="system-ui,sans-serif">500,000 ha</text>
  <!-- legend box (bottom-right; all curves are near the top at this x range) -->
<rect x="458" y="122" width="188" height="88" rx="3" fill="white" fill-opacity="0.95"
     stroke="#d0d7de" stroke-width="1"/>
<line x1="468" y1="141" x2="498" y2="141" stroke="#1a1a1a" stroke-width="2"/>
<text x="503" y="145" font-size="10" fill="#444" font-family="system-ui,sans-serif">Standard formula</text>
<line x1="468" y1="162" x2="498" y2="162" stroke="#2e7d32" stroke-width="1.8" stroke-dasharray="6,3"/>
<text x="503" y="166" font-size="10" fill="#444" font-family="system-ui,sans-serif">Option 2 — stratify</text>
<line x1="468" y1="183" x2="498" y2="183" stroke="#1565C0" stroke-width="1.8"/>
<text x="503" y="187" font-size="10" fill="#444" font-family="system-ui,sans-serif">Option 1 — divide</text>
</svg>
Diagram is schematic — y-axis not to scale across methods. Option 2 shape reflects the tool's log-area correction (n ∝ [1 + log₁₀(area/1000)]²); Option 1 reflects linear summation of ~31 plots per sub-unit.
There are three approaches to fix this, in increasing order of complexity.

---

## Option 1 — Divide your project area into smaller sub-units

The most direct fix: break your project boundary into ecologically meaningful sub-units, run the sample size calculation independently for each, and sum the results. This works well when your landscape has clear natural or administrative divisions — watershed boundaries, management units, or distinct vegetation zones.

**Step 1 — Identify natural divisions**

Use watershed boundaries, management blocks, or vegetation transitions that are ecologically meaningful and can be delineated from field knowledge or existing GIS layers.

**Step 2 — Run the calculation for each sub-unit independently**

Enter the area, variance estimate, and precision targets separately for each zone. Each gets its own *n*, reflecting its own internal variability.

**Step 3 — Sum the results**

Total sample size = sum of all sub-unit *n* values. This is your defensible, area-appropriate sample size for the full project.

> [!TIP]
> **When this works best**
>
> You have pre-existing management units, watershed delineations, or administrative boundaries that also make ecological sense. If your divisions feel arbitrary, consider Option 2 — letting satellite data define where the meaningful boundaries actually are.

---

## Option 2 — Stratification with geospatial tools

Rather than dividing your area arbitrarily, stratification uses satellite imagery and land cover data to divide it *meaningfully* — into zones that are internally similar and externally distinct for carbon stock. Each zone then gets its own share of the total sample size, ensuring no ecosystem type is systematically under-sampled.

### How the tool works

The tool is built in Google Earth Engine and walks through four steps. It uses Canada-wide prior statistics to estimate sample size before any field data is collected, making it suitable for project planning from scratch.

#### Step 1 — Define your area

Draw a polygon directly on the map or load a GEE asset path.

#### Step 2 — Choose how to divide your area

Two stratification methods are available.

**Land cover map (ESA CCI)** — uses the ESA Climate Change Initiative land cover product at 300 m resolution. Two levels of forest detail:

| Class | Standard | Detailed |
|---|---|---|
| Forest | All tree cover merged into one class | Broadleaved / Needleleaved / Mixed |
| Shrubland | ✓ | ✓ |
| Herbaceous | ✓ | ✓ |
| Moss / Lichen / Sparse | ✓ | ✓ |
| Wetland | ✓ includes flooded forest | ✓ includes flooded forest |
| Cropland | Optional — unchecked by default | Optional — unchecked by default |
| Urban / water / bare / snow | Excluded from sampling | Excluded from sampling |

> Treed peatland (open black spruce) maps to Wetland rather than Needleleaved Forest, which is ecologically appropriate for saturated systems. Finer wetland classification (fen/bog/swamp) requires the Canadian Wetland Inventory.

**Satellite imagery zones (AI-based)** — uses Google Satellite Embeddings V1 with fixed-k KMeans clustering (2–10 zones). Automatically groups spectrally similar areas without requiring an existing land cover product. Useful for areas where ESA CCI resolution is too coarse relative to your project boundary.

#### Step 3 — Set your sampling parameters

Sample size is calculated from Canada-wide prior statistics rather than requiring field data upfront. Two project size modes:

- **Smaller project (< 1,000 ha)** — you set an expected coefficient of variation (CV) using a slider. 30% is a reasonable starting point; adjust up if you expect high within-area variability.
- **Larger project (≥ 1,000 ha)** — applies a log-scaled area correction that increases the sample size estimate with landscape size, without growing it linearly. This sits between the flat asymptote of the standard formula and an unrealistic linear increase.

#### Step 4 — Review allocation and export plot locations

The tool shows two allocation options side by side. Both use the same total sample size; they differ only in how plots are distributed across zones:

| Column | Method | Effect |
|---|---|---|
| **Prop.** | Proportional to area | Equal plot density across all zones |
| **Adj.** | Area<sup>0.75</sup> power law | Larger zones get slightly fewer plots per hectare — reflects the sub-linear relationship between area and required sample size |

You choose which allocation to use before exporting. Plot locations are available as CSV, GeoJSON, KML, or Shapefile.

### Video walkthrough

> You can choose to upload a asset to google earth engine, and copy and paste the asset path, or you can draw a polygon from scratch using the drawing tool. 

https://github.com/user-attachments/assets/559353d5-fb23-40ef-b1d4-28ea82f06638






https://github.com/user-attachments/assets/5eb07031-6a74-483b-8331-44eef2a45343








▶ **[Open Tool in GEE](https://ee-cathalpdoherty2.projects.earthengine.app/view/stratification-sampling-tool)** &nbsp;·&nbsp; **[View Source Code](https://github.com/CathalD/NS_Carbon_Edu.git)**

---

## Option 3 — Remote sensing-based methods

Building on Option 2, estimating carbon stocks across large areas often requires spatial extrapolation — using field plots to calibrate a model that predicts carbon at every location across the landscape. This changes the fundamental question from *how many plots do I need to estimate the mean?* to *how many plots do I need to train a model that meets a target prediction accuracy?*

- **The model dictates the samples, not the other way around.** Sample size is determined by the number of training observations required to reach a target prediction error for the spatial model — typically a Random Forest or ensemble approach.
- Remote sensing covariates (spectral indices, canopy height, terrain derivatives) are extracted at each plot location. The sampling design must ensure plots span the full covariate space of the landscape, not just its geographic extent.
- This approach is most appropriate when the project goal is a wall-to-wall carbon map rather than a single mean estimate — for instance, VM0033-compliant baseline mapping across a large project boundary.

> 📹 **Demonstration — remote sensing-based sampling design**
> Video coming soon. Replace this line with an embedded YouTube or Vimeo link.

> [!NOTE]
> **Further reading**
>
> Wadoux et al. (2021). Spatial cross-validation is not the right way to evaluate map accuracy. *Ecological Modelling*, 457, 109692.
>
> Sothe et al. (2022). Large scale mapping of soil organic carbon concentration with 3D machine learning and satellite observations. *Geoderma*, 405, 115402. — Canadian soil and forest carbon priors used in the sampling tool above.

---

Developed by [WWF-Canada / North Star Labs](#) for the [Nature Meets Carbon](#) and Blue Carbon Hub initiatives. Tools are open source and designed for Indigenous-led land stewardship programs and conservation practitioners across Canada.

[GitHub](#) &nbsp;·&nbsp; [GEE Sampling Tool](#) &nbsp;·&nbsp; [Contact](#)
