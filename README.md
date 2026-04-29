<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Large-Area Carbon Sampling — Field Guidance</title>
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, Arial, sans-serif;
    font-size: 16px;
    line-height: 1.6;
    color: #1a1a1a;
    background: #ffffff;
    max-width: 860px;
    margin: 0 auto;
    padding: 40px 24px 80px;
  }

  h1 { font-size: 2em; font-weight: 600; margin: 0 0 8px; border-bottom: 1px solid #d0d7de; padding-bottom: 12px; }
  h2 { font-size: 1.4em; font-weight: 600; margin: 40px 0 12px; border-bottom: 1px solid #d0d7de; padding-bottom: 8px; }
  h3 { font-size: 1.1em; font-weight: 600; margin: 24px 0 8px; }
  h4 { font-size: 1em; font-weight: 600; margin: 16px 0 6px; color: #444; }

  p  { margin: 0 0 14px; color: #333; }
  a  { color: #0969da; text-decoration: none; }
  a:hover { text-decoration: underline; }
  strong { font-weight: 600; }
  em { font-style: italic; }
  code {
    font-family: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, monospace;
    font-size: 0.875em; background: #f6f8fa; border: 1px solid #d0d7de;
    border-radius: 3px; padding: 2px 5px;
  }

  .badges { display: flex; flex-wrap: wrap; gap: 6px; margin: 14px 0 24px; }
  .badge {
    font-size: 12px; font-weight: 500; padding: 2px 10px;
    border: 1px solid #d0d7de; border-radius: 12px; color: #444; background: #f6f8fa;
  }

  .callout {
    border-left: 4px solid #d0d7de; padding: 12px 16px;
    margin: 16px 0; background: #f6f8fa; border-radius: 0 4px 4px 0;
  }
  .callout p { color: #444; font-size: 15px; margin: 0; }
  .callout-title {
    font-weight: 600; font-size: 12px; letter-spacing: 0.05em;
    text-transform: uppercase; margin-bottom: 6px; color: #1a1a1a;
  }

  .option-header {
    display: flex; align-items: baseline; gap: 12px;
    margin: 40px 0 12px; border-bottom: 1px solid #d0d7de; padding-bottom: 8px;
  }
  .option-number {
    font-size: 11px; font-weight: 600; letter-spacing: 0.08em;
    text-transform: uppercase; color: #666; white-space: nowrap;
  }
  .option-header h2 { margin: 0; border: none; padding: 0; font-size: 1.3em; }

  ul, ol { padding-left: 24px; margin: 0 0 14px; color: #333; }
  li { margin-bottom: 6px; }

  table { width: 100%; border-collapse: collapse; font-size: 14px; margin: 16px 0; }
  th { background: #f6f8fa; font-weight: 600; text-align: left; padding: 8px 12px; border: 1px solid #d0d7de; }
  td { padding: 7px 12px; border: 1px solid #d0d7de; color: #333; vertical-align: top; }
  tr:nth-child(even) td { background: #f6f8fa; }

  .steps { margin: 16px 0; }
  .step  { display: flex; gap: 14px; margin-bottom: 14px; }
  .step-num {
    flex-shrink: 0; width: 24px; height: 24px;
    border: 2px solid #1a1a1a; border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 12px; font-weight: 700; margin-top: 2px;
  }
  .step-body h4 { margin: 0 0 4px; }
  .step-body p  { font-size: 15px; color: #555; margin: 0; }

  .video-placeholder {
    border: 1px dashed #d0d7de; border-radius: 6px; padding: 40px 24px;
    text-align: center; margin: 20px 0; color: #888; font-size: 14px; background: #fafafa;
  }
  .video-placeholder strong { display: block; font-size: 15px; color: #555; margin-bottom: 4px; }

  .link-row { display: flex; flex-wrap: wrap; gap: 10px; margin: 20px 0; }
  .btn {
    display: inline-flex; align-items: center; gap: 6px;
    font-size: 14px; font-weight: 500; padding: 7px 16px;
    border: 1px solid #d0d7de; border-radius: 6px;
    color: #1a1a1a; background: #f6f8fa; text-decoration: none;
  }
  .btn:hover { background: #eee; text-decoration: none; }
  .btn.primary { background: #1a1a1a; color: #fff; border-color: #1a1a1a; }
  .btn.primary:hover { background: #333; }

  hr { border: none; border-top: 1px solid #d0d7de; margin: 40px 0; }

  .toc {
    border: 1px solid #d0d7de; border-radius: 6px;
    padding: 16px 20px; margin: 24px 0; background: #fafafa; font-size: 14px;
  }
  .toc-title { font-weight: 600; margin-bottom: 8px; }
  .toc ol { margin: 0; padding-left: 20px; }
  .toc li { margin-bottom: 4px; }

  footer { margin-top: 60px; padding-top: 20px; border-top: 1px solid #d0d7de; font-size: 13px; color: #888; }
  footer a { color: #666; }
</style>
</head>
<body>

<h1>Large-Area Carbon Sampling</h1>

<div class="badges">
  <span class="badge">Nature Meets Carbon</span>
  <span class="badge">WWF-Canada</span>
  <span class="badge">Google Earth Engine</span>
  <span class="badge">Canada</span>
</div>

<p>
  Field guidance for ecologists and land managers who need a defensible sampling design for
  carbon stock estimation across large project areas — and whose standard sample size calculator
  returned a surprisingly small number.
</p>

<div class="link-row">
  <a class="btn primary" href="#">&#9654; Open Sampling Tool</a>
  <a class="btn" href="#">View Source Code</a>
</div>

<div class="toc">
  <div class="toc-title">Contents</div>
  <ol>
    <li><a href="#problem">Why your sample size looks too small</a></li>
    <li><a href="#option1">Option 1 — Divide your project area</a></li>
    <li><a href="#option2">Option 2 — Stratification with geospatial tools</a></li>
    <li><a href="#option3">Option 3 — Remote sensing-based methods</a></li>
  </ol>
</div>

<h2 id="problem">Why your sample size looks too small</h2>

<p>
  To start: you did nothing wrong. The standard sample size formula was designed for small,
  relatively uniform plots. When applied to a landscape of thousands of hectares, it hits a
  statistical ceiling — not because your area is well-sampled, but because the formula assumes
  the entire area is homogeneous.
</p>

<div class="callout">
  <div class="callout-title">The core assumption that breaks down</div>
  <p>
    The formula treats your entire project area as a single, internally consistent population.
    A large landscape spanning multiple ecosystem types, soil depths, and drainage classes will
    have far more internal variability than the model accounts for — and that variability is
    exactly what drives sample size.
  </p>
</div>

<p>
  As area increases, the formula approaches a fixed ceiling determined by variance and your
  precision targets — not by area. For a homogeneous area this is statistically correct.
  For a large, ecologically complex landscape it systematically underestimates how many
  samples you need.
</p>

<svg viewBox="0 0 700 210" xmlns="http://www.w3.org/2000/svg" style="width:100%;display:block;margin:20px 0;">
  <line x1="60" y1="185" x2="660" y2="185" stroke="#ccc" stroke-width="1"/>
  <line x1="60" y1="185" x2="60" y2="18"  stroke="#ccc" stroke-width="1"/>
  <line x1="60" y1="52" x2="660" y2="52" stroke="#bbb" stroke-width="1" stroke-dasharray="5,4"/>
  <text x="665" y="56" font-size="11" fill="#999" font-family="system-ui,sans-serif">ceiling</text>
  <path d="M 60,182 C 110,138 190,78 290,58 C 380,48 460,47 660,46"
        stroke="#1a1a1a" stroke-width="2" fill="none"/>
  <path d="M 60,182 C 120,152 205,118 315,97 C 415,80 515,68 625,60 C 648,58 658,57 660,56"
        stroke="#666" stroke-width="1.5" fill="none" stroke-dasharray="8,4"/>
  <text x="295" y="40" font-size="11" fill="#1a1a1a" font-family="system-ui,sans-serif" font-weight="600">Standard formula (asymptote)</text>
  <text x="460" y="52" font-size="11" fill="#666" font-family="system-ui,sans-serif">Stratified approach</text>
  <text x="360" y="202" font-size="11" fill="#999" text-anchor="middle" font-family="system-ui,sans-serif">Project area</text>
  <text x="22" y="108" font-size="11" fill="#999" font-family="system-ui,sans-serif" transform="rotate(-90,22,108)">Sample size (n)</text>
  <text x="135" y="200" font-size="10" fill="#bbb" font-family="system-ui,sans-serif">500 ha</text>
  <text x="295" y="200" font-size="10" fill="#bbb" font-family="system-ui,sans-serif">10,000 ha</text>
  <text x="480" y="200" font-size="10" fill="#bbb" font-family="system-ui,sans-serif">500,000 ha</text>
</svg>

<p>There are three approaches to fix this, in increasing order of complexity.</p>

<hr>

<!-- ── OPTION 1 ── -->
<div class="option-header" id="option1">
  <span class="option-number">Option 1</span>
  <h2>Divide your project area into smaller sub-units</h2>
</div>

<p>
  The most direct fix: break your project boundary into ecologically meaningful sub-units,
  run the sample size calculation independently for each, and sum the results.
  This works well when your landscape has clear natural or administrative divisions —
  watershed boundaries, management units, or distinct vegetation zones.
</p>

<div class="steps">
  <div class="step">
    <div class="step-num">1</div>
    <div class="step-body">
      <h4>Identify natural divisions</h4>
      <p>Use watershed boundaries, management blocks, or vegetation transitions that are
      ecologically meaningful and can be delineated from field knowledge or existing GIS layers.</p>
    </div>
  </div>
  <div class="step">
    <div class="step-num">2</div>
    <div class="step-body">
      <h4>Run the calculation for each sub-unit independently</h4>
      <p>Enter the area, variance estimate, and precision targets separately for each zone.
      Each gets its own <em>n</em>, reflecting its own internal variability.</p>
    </div>
  </div>
  <div class="step">
    <div class="step-num">3</div>
    <div class="step-body">
      <h4>Sum the results</h4>
      <p>Total sample size = sum of all sub-unit <em>n</em> values. This is your defensible,
      area-appropriate sample size for the full project.</p>
    </div>
  </div>
</div>

<div class="callout">
  <div class="callout-title">When this works best</div>
  <p>You have pre-existing management units, watershed delineations, or administrative
  boundaries that also make ecological sense. If your divisions feel arbitrary, consider
  Option 2 — letting satellite data define where the meaningful boundaries actually are.</p>
</div>

<hr>

<!-- ── OPTION 2 ── -->
<div class="option-header" id="option2">
  <span class="option-number">Option 2</span>
  <h2>Stratification with geospatial tools</h2>
</div>

<p>
  Rather than dividing your area arbitrarily, stratification uses satellite imagery and land
  cover data to divide it <em>meaningfully</em> — into zones that are internally similar and
  externally distinct for carbon stock. Each zone then gets its own share of the total sample
  size, ensuring no ecosystem type is systematically under-sampled.
</p>

<h3>How the tool works</h3>

<p>
  The tool is built in Google Earth Engine and walks through four steps. It uses
  Canada-wide prior statistics to estimate sample size before any field data is collected,
  making it suitable for project planning from scratch.
</p>

<h4>Step 1 — Define your area</h4>
<p>Draw a polygon directly on the map or load a GEE asset path.</p>

<h4>Step 2 — Choose how to divide your area</h4>
<p>Two stratification methods are available:</p>

<p>
  <strong>Land cover map (ESA CCI)</strong> — uses the ESA Climate Change Initiative land
  cover product at 300 m resolution. Two levels of forest detail:
</p>

<table>
  <thead>
    <tr><th>Class</th><th>Standard</th><th>Detailed</th></tr>
  </thead>
  <tbody>
    <tr><td>Forest</td><td>All tree cover merged into one class</td><td>Broadleaved / Needleleaved / Mixed</td></tr>
    <tr><td>Shrubland</td><td>&#10003;</td><td>&#10003;</td></tr>
    <tr><td>Herbaceous</td><td>&#10003;</td><td>&#10003;</td></tr>
    <tr><td>Moss / Lichen / Sparse</td><td>&#10003;</td><td>&#10003;</td></tr>
    <tr><td>Wetland</td><td>&#10003; includes flooded forest</td><td>&#10003; includes flooded forest</td></tr>
    <tr><td>Cropland</td><td colspan="2">Optional — unchecked by default</td></tr>
    <tr><td>Urban / water / bare / snow</td><td colspan="2">Excluded from sampling</td></tr>
  </tbody>
</table>

<p style="font-size:13px;color:#666;margin-top:-6px;">
  Treed peatland (open black spruce) maps to Wetland rather than Needleleaved Forest, which is
  ecologically appropriate for saturated systems. Finer wetland classification (fen/bog/swamp)
  requires the Canadian Wetland Inventory.
</p>

<p>
  <strong>Satellite imagery zones (AI-based)</strong> — uses Google Satellite Embeddings V1
  with fixed-k KMeans clustering (2–10 zones). Automatically groups spectrally similar areas
  without requiring an existing land cover product. Useful for areas where ESA CCI resolution
  is too coarse relative to your project boundary.
</p>

<h4>Step 3 — Set your sampling parameters</h4>

<p>Sample size is calculated from Canada-wide prior statistics rather than requiring
field data upfront. Two project size modes:</p>

<ul>
  <li><strong>Smaller project (&lt;&#8239;1,000 ha)</strong> — you set an expected coefficient
  of variation (CV) using a slider. 30% is a reasonable starting point; adjust up if you
  expect high within-area variability.</li>
  <li><strong>Larger project (&#8239;&#8805;&#8239;1,000 ha)</strong> — applies a log-scaled area
  correction that increases the sample size estimate with landscape size, without growing it
  linearly. This sits between the flat asymptote of the standard formula and an unrealistic
  linear increase.</li>
</ul>

<h4>Step 4 — Review allocation and export plot locations</h4>

<p>The tool shows two allocation options side by side. Both use the same total sample size;
they differ only in how plots are distributed across zones:</p>

<table>
  <thead>
    <tr><th>Column</th><th>Method</th><th>Effect</th></tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>Prop.</strong></td>
      <td>Proportional to area</td>
      <td>Equal plot density across all zones</td>
    </tr>
    <tr>
      <td><strong>Adj.</strong></td>
      <td>Area<sup>0.75</sup> power law</td>
      <td>Larger zones get slightly fewer plots per hectare — reflects the
      sub-linear relationship between area and required sample size</td>
    </tr>
  </tbody>
</table>

<p>You choose which allocation to use before exporting. Plot locations are available as
CSV, GeoJSON, KML, or Shapefile.</p>

<h3>Video walkthrough</h3>

<div class="video-placeholder">
  <strong>Demonstration — large boreal landscape in Ontario</strong>
  Replace with embedded video URL when available.
</div>

<div class="link-row">
  <a class="btn primary" href="#">&#9654; Open Tool in GEE</a>
  <a class="btn" href="#">View Source Code</a>
</div>

<hr>

<!-- ── OPTION 3 ── -->
<div class="option-header" id="option3">
  <span class="option-number">Option 3</span>
  <h2>Remote sensing-based methods</h2>
</div>

<p>
  Building on Option 2, estimating carbon stocks across large areas often requires spatial
  extrapolation — using field plots to calibrate a model that predicts carbon at every
  location across the landscape. This changes the fundamental question from
  <em>how many plots do I need to estimate the mean?</em> to
  <em>how many plots do I need to train a model that meets a target prediction accuracy?</em>
</p>

<ul>
  <li>
    <strong>The model dictates the samples, not the other way around.</strong> Sample size is
    determined by the number of training observations required to reach a target prediction
    error for the spatial model — typically a Random Forest or ensemble approach.
  </li>
  <li>
    Remote sensing covariates (spectral indices, canopy height, terrain derivatives) are
    extracted at each plot location. The sampling design must ensure plots span the full
    covariate space of the landscape, not just its geographic extent.
  </li>
  <li>
    This approach is most appropriate when the project goal is a wall-to-wall carbon map
    rather than a single mean estimate — for instance, VM0033-compliant baseline mapping
    across a large project boundary.
  </li>
</ul>

<div class="video-placeholder">
  <strong>Demonstration — remote sensing-based sampling design</strong>
  Replace with embedded video URL when available.
</div>

<div class="callout">
  <div class="callout-title">Further reading</div>
  <p>
    Wadoux et al. (2021). Spatial cross-validation is not the right way to evaluate map
    accuracy. <em>Ecological Modelling</em>, 457, 109692.<br><br>
    Sothe et al. (2022). Large scale mapping of soil organic carbon concentration with 3D
    machine learning and satellite observations. <em>Geoderma</em>, 405, 115402. — Canadian
    soil and forest carbon priors used in the sampling tool above.
  </p>
</div>

<hr>

<footer>
  <p>
    Developed by <a href="#">WWF-Canada / North Star Labs</a> for the
    <a href="#">Nature Meets Carbon</a> and Blue Carbon Hub initiatives.
    Tools are open source and designed for Indigenous-led land stewardship programs
    and conservation practitioners across Canada.
  </p>
  <p style="margin-top:8px;">
    <a href="#">GitHub</a> &nbsp;&middot;&nbsp;
    <a href="#">GEE Sampling Tool</a> &nbsp;&middot;&nbsp;
    <a href="#">Contact</a>
  </p>
</footer>

</body>
</html>
