# GMT 25 Profiles MT — Mariana Trench Cross-Section Location Map

A GMT (Generic Mapping Tools) shell script that maps the geographic location of a series of 25 cross-sectional profiles along the Mariana Trench. The profile transects are drawn as oriented vectors along the trench axis over an Albers equal-area contour basemap, serving as an index / location map for the profiling geometry. The script has been used to generate figures in the author's marine-geomorphological and cartographic publications.

## What the script does

- extracts a regional relief subset (grdcut) and reports its range (grdinfo)
- draws the bathymetric contour basemap in an Albers equal-area conic projection (grdcontour, -JB)
- plots the 25 profile transects as oriented vectors along the trench axis (psxy -Sv)
- adds title, grid, scale bar and directional rose (psbasemap)
- outlines the study area and adds a labelled boundary (psbasemap -D, psxy -Sq)
- adds annotations, projection notes and the GMT logo (pstext, logo)
- exports to raster (psconvert) at high resolution

This location map is a companion to the cross-section profiling and stacked-profile scripts, showing where each transect is taken.

## Data source

Global relief / bathymetry: ETOPO1 (1 and 5 arc-minute), via GMT earth_relief tiles.

## Requirements

- GMT 6.x (Generic Mapping Tools): https://www.generic-mapping-tools.org
- A POSIX shell (bash/sh)
- An ETOPO1 / earth_relief grid available locally

## Usage

Adjust the -R region, -J projection and the profile coordinates at the top of the script, then run:

    bash GMT-13-JB-25profiles-MT.sh

The script writes a PostScript file and converts it to a raster image (JPG/PNG) via psconvert.

## Author and citation

Polina Lemenkova
ORCID: https://orcid.org/0000-0002-5759-1089

This script supports figures in the author's marine-geomorphological and cartographic papers; please cite the specific article a given figure appears in. The full publication list is available via the ORCID record above.

## License

See the LICENSE file in this repository.
