---
title: Inspect CSS Grid
description: Using Microsoft Edge DevTools to view and change the CSS of a page CSS.
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: conceptual
ms.prod: microsoft-edge
ms.date: 05/04/2021
---
# Inspect CSS Grid

This article walks you through identifying CSS grids on a website and debugging grid layout issues using customizable grid overlays.

The examples used in the figures in this article are taken from the following webpages:
* [Fruit box](https://jec.fyi/demo/css-grid-fruit)
* [Snack box](https://jec.fyi/demo/css-grid-snack)


<!-- ====================================================================== -->
## Before you begin

CSS Grid is a powerful layout paradigm for the web.  A great place to get started learning about CSS Grid and the many features is the [CSS Grid Layout guide](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) on MDN.


<!-- ====================================================================== -->
## Discover CSS grids

When an HTML element on your page has `display: grid` or `display: inline-grid` applied to it, a `grid` badge is displayed next to it in the [Elements](../open/index.md) panel.

:::image type="content" source="../media/grid-discover-grid.msft.png" alt-text="Discover grid." lightbox="../media/grid-discover-grid.msft.png":::

Click the badge to toggle the display of a grid overlay on the page.  The overlay appears over the element, laid out like a grid to display the position of the grid lines and tracks:

:::image type="content" source="../media/grid-highlight-grid.msft.png" alt-text="Toggle grid badge." lightbox="../media/grid-highlight-grid.msft.png":::

Open the **Layout** pane.  When grids are included on a page, the **Layout** pane includes a **Grid** section containing a number of options for viewing the grids.

:::image type="content" source="../media/grid-layout-pane.msft.png" alt-text="Layout pane." lightbox="../media/grid-layout-pane.msft.png":::

The **Grid** section in the **Layout** pane contains the following 2 sub-sections:

*  Overlay display settings
*  Grid overlays

<!--todo: verify the details for each of the sub-sections -->


<!-- ====================================================================== -->
## Overlay display settings

In the **Layout** tab, in the expandable **Grid** section, the **Overlay display settings** section contains the following UI.

### Dropdown list

Select one of the following options from the dropdown list:

| Line option | Details |
|:--- |:--- |
| **Hide line labels** | Hide the labels of the lines for each grid overlay. |
| **Show line numbers** | Display the numbers of the lines for each grid overlay (selected by default). |
| **Show line names** | Display the names of the lines for each grid overlay when names are provided. |

The following sections explain the **Overlay display settings** dropdown list commands.

#### Hide line labels

In the dropdown list, select **Hide line labels** to hide the labels of the lines for each grid overlay.

:::image type="content" source="../media/grid-hide-line-labels.msft.png" alt-text="Hide line labels." lightbox="../media/grid-hide-line-labels.msft.png":::

#### Show line numbers

In the dropdown list, select **Show line numbers** to display the numbers of the lines for each grid overlay (selected by default).

By default, the positive and negative line numbers are displayed on the grid overlay.

For more information about negative numbers in the grid overlay, see [Line-based placement with CSS Grid](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Line-based_Placement_with_CSS_Grid).

:::image type="content" source="../media/grid-show-line-numbers.msft.png" alt-text="Display line numbers." lightbox="../media/grid-show-line-numbers.msft.png":::

#### Show line names

In the dropdown list, select **Show line names** to view the line names instead of numbers; this displays the names of the lines for each grid overlay when names are provided.  In the example, 4 lines have names: `left`, `middle1`, `middle2`, and `right`.

For more information about line names in the grid overlay, see [Layout using named grid lines](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout/Layout_using_Named_Grid_Lines).

<!--In the demo, **orange** element spans from left to right, with `grid-column: left` and `grid-column: right` CSS.  Showing line names makes it easier to visualize the start and end position of the element.  -->

:::image type="content" source="../media/grid-show-line-names.msft.png" alt-text="Show line names." lightbox="../media/grid-show-line-names.msft.png":::

### Checkboxes

Select any of the checkboxes in the **Overlay display settings** section:

| Option | Details |
|:--- |:--- |
| **Show track sizes**  | Display (or hide) the sizes of the tracks. |
| **Show area names** | Display (or hide) the names of the area, when names are provided. |
| **Extend grid lines** | Displays (or hides) the extensions of the grid dimensions along each axis.  By default, grid lines are only shown inside the element with `display: grid` or `display: inline-grid` CSS set on it. |

The following sections explain these checkboxes.

#### Show track sizes

Select the **Show track sizes** checkbox, to view the track sizes of the grid.

DevTools displays `[authored size]` and `[computed size]` in each line label.

| Size | Details |
|:--- |:--- |
| **authored size** | The size defined in stylesheet (omitted if not defined). |
| **computed size** | The actual size on screen. |

In the demo, the `snack-box` column sizes are defined in the `grid-template-columns:1fr 2fr;` CSS.  Therefore, the column line labels display both authored and computed sizes.

| Track size | Authored size | Computed size |
|:--- |:--- |:--- |
| **1fr** &#x2022; **96.66px** | 1fr | 96.66px |
| **2fr** &#x2022; **193.32px** | 2fr | 193.32px |

The row line labels display only computed sizes, since there are no row sizes defined in the stylesheet.

| Track size | Authored size | Computed size |
|:--- |:--- |:--- |
| **80px** | &nbsp;| 80px |
| **80px** | &nbsp;| 80px |

:::image type="content" source="../media/grid-show-track-sizes.msft.png" alt-text="Show track sizes." lightbox="../media/grid-show-track-sizes.msft.png":::

#### Show area names

To view the area names, select the **Show area names** checkbox.  In the example, there are 3 areas in the grid: **top**, **bottom1** and **bottom2**.

:::image type="content" source="../media/grid-show-area-names.msft.png" alt-text="Show area names." lightbox="../media/grid-show-area-names.msft.png":::

#### Extend grid lines

Select the **Extend grid lines** checkbox to extend the grid lines to the edge of the viewport along each axis.

:::image type="content" source="../media/grid-extend-grid-lines.msft.png" alt-text="Extend grid lines." lightbox="../media/grid-extend-grid-lines.msft.png":::


<!-- ====================================================================== -->
## Grid overlays

The **Grid overlays** section contains a list of grids that are present on the page, each with a checkbox, along with various options.

### Enable overlay views of multiple grids

To display the overlay grid for multiple grids, select the checkbox next to each name of the grid.  In the example, there are 2 grid overlays enabled, that are each represented with different colors:

*  `main`
*  `div.snack-box`

:::image type="content" source="../media/grid-grid-overlays.msft.png" alt-text="Enable overlay views of multiple grids." lightbox="../media/grid-grid-overlays.msft.png":::

### Customize the grid overlay color

To open the color picker and customize the grid overlay color, click the box next to the name of the grid overlay:

:::image type="content" source="../media/grid-grid-overlays-color.msft.png" alt-text="Customize the grid overlay color." lightbox="../media/grid-grid-overlays-color.msft.png":::

### Highlight the grid

To highlight the HTML element in the **Elements** tool and scroll to it on the webpage, click the **Show element in the Elements panel** (![Show element in the Elements panel icon.](../media/show-element-in-element-panel-icon.msft.png)) icon.

:::image type="content" source="../media/grid-grid-overlays-highlight.msft.png" alt-text="Highlight the grid." lightbox="../media/grid-grid-overlays-highlight.msft.png":::


<!-- ====================================================================== -->
> [!NOTE]
> Portions of this page are modifications based on work created and [shared by Google](https://developers.google.com/terms/site-policies) and used according to terms described in the [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0).
> The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/grid) and is authored by [Jecelyn Yeen](https://developers.google.com/web/resources/contributors#jecelyn-yeen) (Developer advocate, Chrome DevTools).

[![Creative Commons License.](https://i.creativecommons.org/l/by/4.0/88x31.png)](https://creativecommons.org/licenses/by/4.0)
This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0).
