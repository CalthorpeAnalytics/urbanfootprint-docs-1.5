<div style="
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-around;
    display: flex;">
    <img src="images/uf_logo.png" alt="UF_Logo" style="width: 300px; text-align: center;"/>
</div>

<br>

<div style="
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-around;
    display: flex;">
    <img src="images/Analytics_Logo_GreyLetters.png" alt="scag_logo" style="width: 300px;"/>
</div>

<div style="
    justify-content: space-around;
    display: flex;
    margin-top: 10px;">
    <span>
        © 2016 Calthorpe Analytics
    </span>
</div>

<br>

# UrbanFootprint v. 1.5 - User Guide

UrbanFootprint 1.5 is a web based, open source, scenario planning platform. This documentation
covers basic functionality for scenario planning and editing on UrbanFootprint's Scenario
Planning Platform.


## System Requirements

UrbanFootprint is accessed via a web page. For access, there are fairly minimal requirements:

* A relatively recent (purchased in last 5 years) desktop or laptop computer running the Windows, Mac OSX,
or Linux operating systems. The current system has not been optimized for tablet or touchscreen operating
systems or interfaces.

* Current version of Google Chrome web browser. Chrome is available via free download at
[https://www.google.com/intl/en/chrome/browser/](https://www.google.com/intl/en/chrome/browser/)

* Mouse, track-ball, or trackpad-based input device (essentially all desktop or laptop
computers have this capability).

> **Note:** If you experience difficulties in performing feature editing (e.g., feature
selection, querying, etc.) while being able to view maps on UrbanFootprint, first check your
internet firewall configuration with local IT support. The URL of UrbanFootprint should be added to the trust list of firewall configuration in order to avoid block
access by web filters set up locally.

## Site Map

![site_map](images/site_map.png)

## User Interface Overview

## 1. Layer Management Window

The Layer Management window on the left side of the user interface displays layers that
have been preloaded into UrbanFootprint, and that can be turned on for display and activated for
selection, editing, and queries.

The Layer Management window is broken up into 4 sections:

* **Analysis Results**
* **Basemaps**
* **Reference Layers**
* **Future Scenario Layers** *when viewing a future scenario*

The user can select an active layer by clicking on the layer name. The active layer will then highlight in blue.

![editable_layers](images/editable_layers.png)
> **Example:** Existing Land Use Parcels is visible on the map (checkbox) and is the active
layer (blue highlight).

**Important:** Any map selection, attribute query, export
layer, export csv initiated by the user will occur on the
active layer regardless of whether it is visible or not.

Each layer's legend is viewable by clicking on the arrow in front of the layer and then
expanding the arrow that appears below the layer.

![layer_management_legend](images/layer_management_legend.png)

[layers_icon]: <images/layers.png>
[reorder_arrow]: <images/reorder_arrow.png>
[reorder_layers]: <images/reorder_layers.png>

*Editable Layer*: Any layer under the Editable Layers section contains editable fields by
the user. See Appendix B for the list of editable fields.



![Layers Button][layers_icon] *Exporting Active Layer*: The user can export the Active
Layer to a geodatabase (.gdb) by clicking on the layers button on the Layers Tool Bar.
The user can initiate exporting by clicking ‘OK’ on a window that opens up once the user
clicks on the ‘Export Active Layer – to gdb’ button.  By default, the exported layer is
saved to the user's default Download folder.

![Reorder Arrow][reorder_arrow] *Reordering Map Layers*: The user can re-order layers on
the map by clicking on the arrow button on the right side of the Layers Tool Bar. This
button will open a window where the user can order the layers by clicking on the layer name
and dragging it into the order the user prefers within the visible list. This order
corresponds to the layer order on the map.

![Re-Order Layers][reorder_layers]

## 2. Map Tool Bar

Clicking on an icon on the map tool bar allows the user to zoom and navigate around the map
as well as select and identify map features. The user can hover their pointer to get the
‘tool tip’ to identify what button corresponds with each selector.

[selector_tools]: <images/selector_tools.png>
![Toolbar][selector_tools]

[extent_selector]: <images/extent_selector.png>
[zoom_selected]: <images/zoom_selected.png>
[cancel_select]: <images/cancel_select.png>
[hand_select]: <images/hand_select.png>
[pointer_select]: <images/pointer_select.png>
[box_select]: <images/box_select.png>
[polygon_select]: <images/polygon_select.png>
[info_select]: <images/info_select.png>
[download_select]: <images/download_selector.png>


![Zoom to Extent][extent_selector] *Zoom to Project Extent*: This tool allows the user to
zoom the current map to the project extent. The project refers to the project selected in
the Active Project dropdown in the header bar.

![Zoom to Selection][zoom_selected] *Zoom to Selection Extent*: This tool allows the user to
zoom the current map to the extent of selected features of the Active Layer.

![Clear Selection][cancel_select] *Clear Selection*: This tool clears the selected features
of the Active Layer.

![Navigate][hand_select] *Navigate*: This tool allows the user to navigate around the map by
clicking and dragging on the map. **Tip:** The user can hold ‘Shift’ and drag to zoom to a specific extent.

![Identify][info_select] *Identify*: This tool is activated when features are selected. The
Identify tool opens a moveable summary window where the user can view the attributes of the selected feature.

![Point Selector][pointer_select] *Point Selector*: The point selector selects a single
feature on the map.

![Rectangle Selector][box_select] *Rectangle Selector*: The rectangle selector selects the
features that intersect with a rectangle formed by the user clicking and dragging across the map.

![Polygon Selector][polygon_select] *Polygon Selector*: The polygon selector selects the
features that intersects with a user-defined polygon shape formed by the user defining each
node of the polygon by clicking on the map. Double clicking will stop forming the polygon selection.

![Download Selector][download_select] *Export Map*: The Export Map buttons takes a snapshot of
the current map and downloads the map as a jpg to the user's default Download folder.

> **Tip:** ***Multi-select*** can be activated by holding down the CTRL/CMD key (Windows/Mac)
for the Point ![Point Selector][pointer_select], Rectangle ![Rectangle Selector][box_select],
and Polygon ![Polygon Selector][polygon_select] Selectors.


## 3. Top Section Menu Pane

The top section menu drop down allows the user to toggle between Scenario Info and Data Explorer options. After clicking one of the options, the map selection will resize
to display the selected option.

[menu_button]: <images/menu_button.png>
[approval_merge]: <images/approval_icon.png>
[data_explorer]: <images/query.png>
[scenario_info]: <images/chart_icon.png>

The user can toggle between the following options by clicking on the menu button:

**Scenario Info:** The user can manage scenarios and view charts of key demographic statistics.

**Data Explorer:** The user can view and explore data in a table view and define attribute
queries and join tables to explore and select data.


## 3.1 Scenario Info ![Scenario Info][scenario_info]

The scenario info section allows users to manage their scenarios and displays charts on Population,
Households, and Employment on the active scenario.

![Scenario Info](images/scenario_info_top_section.png)

### Managing Scenarios

The Manage Scenarios pane can be accessed in the Scenario Info Pane under the ![Manage Scenarios Arrow](images/manage_scenarios_arrow.png) dropdown.

The Manage Scenarios pane allows users to:

-   Select a scenario
-   Create a scenario
-   Delete a scenario

> Note: for editing a scenario see the Scenario Editor section

![Manage Scenarios](images/manage_scenarios.png)

-   Create a New Scenario

> -   Click on the 'plus' icon next to an already existing scenario

*Note:* When starting a new scenario, it is a good idea to create a copy of
the Scenario A that is automatically created to use as the starting
point for any other new scenarios. Basically, the first thing that you
do is make a copy of Scenario A to a "New Scenario Template" and any
time you want to make another scenario you do so by making a copy of the
template.

-   Copy a Scenario

> -   Click on the plus icon next to a scenario name.

-   Delete a Scenario

> -   Click on the 'x' icon next to the scenario

-   Edit Scenario Details

> -   Double click and edit text
> -   Click Save

### Charts

![image](images/charts.png)

Charts:

-   Provide immediate feedback on the Scenario
-   By Increment and End State
-   Population, Dwelling Unit, and Employment Totals
-   Dwelling Units by Type
-   Employment by Type

## 3.2 Data Explorer ![Data Explorer][data_explorer]

The data explorer query functionality and the map selector tools in UrbanFootprint are linked by default.
When a user selects features on the map with the map selector tools, the attributes will populate
in the query table window. If the user inputs an attribute query with no map selection, the map
will show the features selected from the attribute query. The user also has the option to use
attribute selections and map selections in combination.

**Querying Attributes**:
> attribute querying functionality utilizes SQL syntax to tell the database what features the
user would like to select. The user can select attribute names from a drop down list by clicking
on the arrow button next to the ‘Where’ clause or type them in.

![query_ui](images/query_ui.png)

*The following comparison/equality operators are supported:*

* Greater than : >
* Less than : <
* Greater than or equal to : >=
* Less than or equal to : <=
* Equals : =
* Not equal: !=

*For querying strings, the following syntax can be used (must be capitals):*

* BEGINS_WITH : String begins with a certain letter or group of letters
* ENDS_WITH : String ends with a certain letter or group of letters
* CONTAINS: String contains a certain letter or group of letters

*Multiple attribute queries are supported using the following syntax (must be capitals):*

* AND : SQL ‘and’ syntax, attributes must meet both query requirements
* OR : SQL ‘or’ syntax, attributes must meet either query requirements

> **Tip:** User can access drop down menus of attributes, operators, and AND/OR/parenthesis
syntax for a quicker query.

**Query Examples:**

 **Example 1**

 Returns all rows with land use code 1200 with a dwelling unit count greater than 2:

    land_use = 1200 AND du >= 2

 **Example 2**

 Returns all parcels with an apn that begins with 580 or an apn that begins with 104:

    apn BEGINS_WITH "580" OR apn BEGINS_WITH "104"

>**Note:** Any string query must have quotation marks around values.


**Joining Tables:**

UrbanFootprint allows the user to join and query spatial tables of different geography types and geographic
scales. The user utilizes these pre-defined join tables by selecting the desired table from the
drop down button in the query window. Having selected a table to join, the user will have access
to all fields in that join table.

>**Important:** If the user is querying a field from the join table that has the same name as a
field in the source table, the system defaults to the source table field. To query the join table
field, the user must write the *name_of_join_table.field_name* or select it from a drop down list
by clicking the arrow next to the 'Where' clause in the Query window.



**Query Options:**

The user has a number of options to form their query and to show helpful information in the user interface:

![query_ui_limit_results](images/query_ui_limit_results.png)

* Limit Results to Selected Area: If the user has selected features with a map selector tool and input
an attribute query, they have the option to limit the query result to the map selection or apply
them to the whole dataset.
* Clear Button: Clears the selection
* Query Button: Executes the query
* Select Attributes Shortcut: Allows user to select from a drop down of attributes
* Operators Shortcut: Allows user to select operators from a drop down list
* AND/OR shortcut: Allows user a shortcut to the common AND/OR/parenthesis operators


## 4. Scenario Editor


![Scenario Map Structure 1](images/map_structure_1.svg)

UrbanFootprint builds a scenario by adding the “change” or “increment”
that you’ve painted on top of a base conditions dataset. The combination
of the two produces what is known as the “End state.” The “End State”
represents what will be on the ground in the future (at what ever time
you’re targeting).

![Scenario Map Structure 2](images/map_structure_2.svg)

It is important to note that this isn’t just a simple addition or
replacement of the base condition with the change map. UrbanFootprint
implements rules that play several roles to control how overlaps are
handled.

*Infill/Redevelopment:* As you add changes you are also defining for
those changes whether any overlaps with the base condition should be
treated as Infill where much of the existing land use is left in place,
and additional development is added to fill in any available capacity.
Alternately the existing condition can be cleared from the parcel to
represent a full reconstruction of the location.

*Development Constraints:* Layers can be added to the scenario that
constrain development in locations that overlap. More on these later.

### Selecting Polygons to Edit

**Hand Selection (Painting)** Manual editing by selecting parcels using
one of the selection tools.

-   Point (image)
-   Line (image)
-   Polygon (image)

Select the tool

-   Box (drag and hold)
-   Polygon (click to draw the shape, double click to finish)

Draw the area you want to include in your selection

Any parcel that touches the shape will be selected

**Query Based**

-   Select parcels based on a query
-   Useful for large area edits or applying changes to a large number of
    parcels that satisfy a conditon.

Work Flow:

1.  Build your query
2.  Apply the query
3.  Apply the Place Type


### Scenario Builder

![image](images/scenario_builder_placetype_list.png)

The scenario builder is where you specify the details about the place
type that you're about to apply to a set of selected polygons. While
you're not changing the fundamentals of the place type (to do that use
the Place Type editing tools), you can specify the percentage of the
available land that will have the place type applied to it, scale the
density of the place type down, and let UrbanFootprint know whether to
overwrite any existing place types (full redevelopment) or to use any
available vacant space in the polygon for the place type.

You can select the set of place types you're working with by clicking on
the button highlighted in red in the image to the left.

-   Development Pct.
-   Density Pct.
-   Gross/Net Pct.
-   Clear Base Condition
-   Redevelopment Flag
-   Apply
-   Undo / Redo

### Development Percent and Density Percent

Development and density percentage controls

Development Pct.:

> The percentage of the parcel land area to receive the place type. 50%
> means that 50% of the available land area will have the place type
> applied to it. In the graphic half of the parcel has development an
> the other half does not after applying the place type.

Density Pct.:

> The percentage of the place type densities to apply. 80% means that a
> place type with an average density of 10 du/acre will be applied
> having 8 du/acre. Note in the graphic the reduced intensity of the
> right parcel when compared to the left one.

### Gross/Net Percentage

Gross/Net Percentage Control

-   Allows assignment of a portion of the space to “No Use”
-   This is used to reserve space for other uses such as drainage,
    parks, or other infrastructure.
-   This is applied to the developable percentage.
-   For Example: If Dev. Pct is 90% and Gross Net is 90% then 9% of the
    parcel would be set aside as “No Use.”

> -   Assume that we've got a 100 acre parcel
> -   Developable space = (100 acres) \*90% = 90 acres
> -   No Use space percentage = 100%-90% = 10%
> -   No Use space = (90 acres) \* 10% = 9 acres

### Clear Base Condition and Redevelopment Flag

Clear Base Condition

> If selected this removes any prior place type from the parcel. If this
> is not selected, new place types are applied only to the portion of
> the parcel’s areas set in the Development Percent box.

**Example:**

Redevelopment Flag

> Manually flag a parcel as having been redeveloped. This control is
> specific to the version of UrbanFootprint with customizations for
> SACOG.

### Applying Land Use

![image](images/scenario_builder_before.png)

To apply a land use to a parcel in the active scenario:

1.  Activate the End State layer
2.  Select the Parcels
3.  Select the Place Type using the Scenario Builder
4.  Adjust Settings for the Place Type
> 1.  Dev, Density, Gross/net: Specify the intensity with which the
>     Place Type will be applied.
> 2.  Clear Base Condition: Do you want to clear the existing
>     land (redevelopment) or not (infill).
> 3.  Redevelopment Flag: track where redevelopment was applied
5.  Apply Place Type

*While setting the densities, keep an eye on the handy pop-up at the
bottom of the screen that tells you how many dwelling units and
employees your settings will create.*

![image](images/scenario_builder_bottom_ribbon.png)

The final result:
![image](images/scenario_builder_after.png)


To save changes to edited attributes the user must click the apply button when finished editing. If the user
changes the selected features without applying changes, those changes will not be saved.

### Undo / Redo
The undo and redo functionality allows users to undo or redo their most recent changes on the active layer.

***Undo: *** Clicking the undo button (back arrow) will undo the most recently saved change on the active scenario regardless of
the current selection.

***Redo: *** Clicking the redo button (forward arrow ) will redo the most recent change that was made using the undo button
regardless of the current selection.

**Tip: ** If the user hovers of the undo or redo buttons, they will see a message with the above definitions.

## 5. Analysis Modules

![image](images/AnalysisModules_overview.png)

Analysis modules are generally run following the completion of a
scenario, or at "break points" within the development of a scenario to
evaluate how the scenario is performing. Some of these analytical
modules take a few minutes to run and as such aren't something that is
run following every change to the scenario.

As shown in the image above, many of the analytical modules are
connected to each other. For example, several of the analytical modules
use outputs generated by running the transportation analytical module.

### Building Energy Use

![image](images/AM_BuildingEnergy.png)

Each building type in UrbanFootprint consumes a baseline amount of
energy based on its location and designated policy factors. Residential
energy use is computed based on each dwelling unit, by type, and
commercial by their square footage by usage (i.e. retail, office,
industrial…).

The location determines which climate zone the building is in, and that
determines the baseline energy consumption. The California Energy
Commission's Title 24 Building Standard climate zones are used for
residential energy factors and the Forecasting Climate Zones are used
for commercial energy use.

![image](images/UF_TD_climatezones.png)

Baseline residential energy use factors are developed from the CEC's
Residential Appliance Saturation Survey (RASS), in this case the 2009
dataset was used.

![image](images/UF_TD_9.1.png)

Energy use in common areas of mixed use and multifamily structures is
estimated based on the CEC's Commercial End-Use Survey (CEUS) data for
lodgings.

The baseline energy use for commercial structures is developed from the
CEUS data sets as Energy Intensity (EI), the energy used per square
foot, for 14 building types, classified by CEC Forecasting Climate Zone.

![image](images/UF_TD_9.3.png)

Baseline energy consumption is assumed to be fixed with the exception of
an incremental improvement in efficiency over time. Buildings present in
at the base line year, can have a rate of retrofitting or replacement
(with the same building type) which improve those building’s energy
efficiency.

New buildings constructed through the scenario have policy driven
baseline improvements in energy efficiency and then are also subject to
rates of retrofitting and replacement.

![image](images/UF_TD_9.5.png)

Energy policy options are implemented through applying rates of
improvement in baseline efficiency to buildings that are either new
construction or are retrofitted, with new construction (or major
retrofits) being a full update to the projected energy efficiency at the
time of construction and retrofits being a significant improvement over
the baseline efficiency that the building had prior to retrofit.

![image](images/UF_TD_9.4.png)

After generating total energy used, assumed costs for electricity and
natural gas can be applied allowing the calculation of energy costs.
Similarly, based on the energy consumed and the potential sources of
that energy GHG emissions may be calculated.

![image](images/UF_TD_9.6.png)

The calculations that determine the number and age of units or
commercial use follow two paths:

-   Existing units experience retrofits and upgrades based on the start
    year energy efficiency. Replacements of these units move to the new
    unit queue reducing the number of units being tracked as part of the
    existing stock.
-   New units are tracked and have the potential for both replacement
    and retrofit as time passes.

![image](images/SACOG_BuildingEnergy.png)

### Water Use

-   Water impacts follow a very similar path to Energy.
-   Building type and climate zone determine baseline water used both
    indoor and outdoor
-   Indoor water usage is estimated per-capita by building type
    -   Residential

![image](images/UF_TD_10.1.png)

-   Commercial is estimated based on three employment types, commercial,
    institutional, and industrial.

![image](images/etozonemap.jpg)

-   Outdoor water usage is estimated per square foot of irrigated
    outdoor space adjusted by the climate zone.
    -   Within 18 climate zones the California DWR provides monthly and
        yearly ETo (reference evapotranspiration values). These are a
        measure of the amount of water needed to support landscaping.
        Based on these, we can estimate the water required per acre of
        landscape.

![image](images/UF_TD_10.2.png)

![image](images/UF_TD_10.3.1.png)

![image](images/UF_TD_10.3.2.png)

-   Consumption rates are then adjusted to account for efficiency and
    conservation improvements in future years.

    -   Like Energy, water consumption by buildings assumes rates of
        efficiency improvements as well as retrofitting or building
        replacements or major renovations.

    ![image](images/UF_TD_10.4.png)

The calculations that determine the number and age of units or
commercial use follow two paths:

-   Existing units experience retrofits and upgrades based on the start
    year energy efficiency. Replacements of these units move to the new
    unit queue reducing the number of units being tracked as part of the
    existing stock.
-   New units are tracked and have the potential for both replacement
    and retrofit as time passes.

### Local Fiscal Impacts

![image](images/AM_LocalFiscal.png)

Fiscal impact analysis divides the build landscape across three axes.
Urban, compact, or standard developments (Land Development Class or
LDC), refill or greenfield construction (development condition), and
housing type (single family detached large lot, single family detached
small lot, single family attached, and multi-family. This version of the
fiscal analysis module applies only to residential development.

![image](images/AM_LocalFiscal2.png)

Urban is high density development characterized by city centers Compact
is a highly walkable, mixed use urban form Standard includes most
suburban, auto-oriented construction.

Infrastructure costs are calculated per residential unit by type, LDC,
and greenfield or refill type. Infrastructure costs are assumed to be a
one time cost. And include the installation of transportation, water,
and waste water facilities.

![image](images/UF_TD_12.3.png)

Operations & Maintenance costs are long term infrastructure related
costs assessed over time on a per residential unit basis by building
type and LDC.

![image](images/UF_TD_12.5.png)

Local Revenues include the projected property tax, property transfer,
and vehicle license fees based on the building type and LDC. i.e. Urban
areas have lower vehicle ownership and the estimates reflect that in the
vehicle license fees.

![image](images/UF_TD_12.6.png)

### Transportation

![image](images/AM_Transportation.png)

Transportation is the most complex of the analytical modules and may
require a half hour or more to run.

Put simply, UrbanFootprint builds a picture of the land use and
accessibility surrounding each housing unit and applies an enhanced
version of the MXD model developed by Fehr & Peers with EPA funding
(<http://www.epa.gov/smartgrowth/mxd_tripgeneration.html>) to
appropriately scale per capita VMT estimates drawn from a local
transportation model up or down as the land use mixture changes.

These results are then fed into a secondary model that applies
projections of future vehicle fleet mixtures and efficiencies to obtain
estimates of the quantity and types of energy used to power the fleet,
the number and length of trips made, the pollutants emitted, and the
costs both for fuel and vehicle O & M.

The results from the Transportation module have matched very well with
MPO travel models. It is important to note that this requires careful
calibration to achieve.

![image](images/TransportValidation.png)

The results from the Transport Module can be displayed visually and in
tabular forms. For example these results are from the Vision California
project by Calthorpe Associates (now Calthorpe Analytics) and display
VMT per household for the Sacramento Area Council of Governments' 2035
land use projections with accompanying info graphic showing a comparison
of two scenarios.

![image](images/TransportSACOG2035.jpg)

![image](images/TransportEngine1.png)

UrbanFootprint incorporates a comprehensive ”sketch” travel model that
interacts with regional travel network data to produce vehicle miles
traveled (VMT), mode choice, and congestion estimates for land use +
transportation scenarios, as well as transportation-related costs,
greenhouse gas (GHG) emissions, and pollutant emissions. The core of
UrbanFootprint’s travel engine was adapted from the MXD model (described
below) created by Fehr & Peers, an internationally-known firm
specializing in state of the art travel behavior research and
prediction.

The MXD method allows differentiation among a broad array of land use
Place Types, the building blocks of UrbanFootprint, calculating the
vehicle trip reductions resulting from the specific combination of D
variables that characterize each Place Type. MXD transportation-demand
relationships allow the combination of intrinsic D variables for a
specific Place Type, coupled with the extrinsic factors that describe
the place’s location within the region, to dictate the degree to which
the place generates more or less vehicle travel than the regional
average.

Costs and emissions estimates for each scenario are based on policy
inputs, which allow the user to see the quantification of the effects of
variations in factors including: fuel price; the carbon content of
fuels; vehicle fuel economy; vehicle fleet turnover; and the
relationship between a widespread shift to vehicle electrification and
the carbon intensity of the electricity generation portfolio.
UrbanFootprint thus Figure 7-1: Overview of the UrbanFootprint travel
engine allows users to quickly and easily see the transportation-related
impacts of the changes in transportation systems, urban form and
regional development patterns between various land use and
transportation scenarios.

### Travel Forecasting in UrbanFootprint

The travel forecasting capabilities within UrbanFootprint are based on a
comprehensive body of research on the relationships between travel
generation and the characteristics of the built environment. The
supporting research includes:

-   Travel and the Built Environment; Ewing and Cervero; 2010
-   Traffic Generated by Mixed-Use Developments—Six-Region Study; Ewing
    and Walters, et al; 2011. (Included as Appendix B of this report.)
-   2010 California Regional Transportation Plan Guidelines, California
    Transportation Commission
-   Assessment of Local Models and Tools for Analyzing Smart-Growth
    Strategies; Caltrans , DKS; 2007
-   Growing Cooler – The Evidence on Urban Development and Climate
    Change; Ewing and Walters et.al.; 2008
-   Guidelines for Quantifying the GHG Effects of Transportation
    Mitigation, California Air Pollution Control Officers Association,
    2010

This and other research have found that urban form, transportation
supply and management policies affect vehicle miles traveled (VMT),
automobile and transit travel through at least eight mechanisms,
referred to as the “8Ds”.

### Measurement of the ‘8Ds’ in UrbanFootprint

The UrbanFootprint travel engine uses the findings from California and
nationwide MXD research to quantify the transportation effects of
differences in transportation and development form ranging from
highly-sustainable compact, mixed and transit-oriented forms to land use
patterns that are more auto-dependent. This relies upon measurement of
each of the following ‘8Ds’ for each micro-scale development area (each
5.5-acre land use grid cell).

1.  *Density* – Dwellings and jobs per acre of development.
2.  *Diversity* – Mix of housing, jobs and retail, measured in terms of
    ratios such as jobs/housing, retail/housing and jobs mix (closeness
    to a balance among uses).
3.  *Design* – Connectivity and walkability, measured in terms of how
    fine-grained the circulation networks through metrics of network
    density, such as walkable street intersections per square mile
4.  *Destinations* – Regional accessibility to activities from the
    regional travel model networks “skim matrices” of travel distances
    and travel times among all development areas or travel analysis
    zones (TAZs).
5.  *Distance to Transit* – Proximity to fixed-guideway service measured
    from the UrbanFootprint development grid cell to the nearest transit
    stops, and expressed in terms of transit stops within walking radii
    of 1⁄4 and 1⁄2 mile.
6.  *Development Scale* – Absolute local amounts of population and jobs
    within the development grid cell’s neighborhood (critical mass and
    magnitude of compatible uses), measured in terms of a 1⁄2 mile
    walking radius
7.  *Demographics* – Household size, income and auto ownership of the
    residential development types contained in the grid cell.
8.  *Demand Management* – Automobile travel disincentives, including
    regional pricing of auto travel through fuel costs, mileage-based
    fees and taxes and parking charges (Method has been developed, but
    is not implemented in UrbanFootprint version 1.0).

UrbanFootprint quantifies the relationships to the first seven “Ds”
through a series of equations from the most recent and rigorous
statistical study: Traffic Generated by Mixed-Use
Developments—Six-Region Study Using Consistent Built Environmental
Measures, prepared for the US EPA and reviewed by the American Society
of Civil Engineers. The study developed hierarchical models that capture
the relationships between the “D” factors and the amount of travel
generated by over 230 mixed-use developments of a wide variety of
settings and sizes across the US, including the Sacramento and San Diego
regions. The predictive accuracy of the methods were validated through
field surveys of traffic at almost 30 other development sites, more than
half of which are located in California, at locations in San Diego,
Orange County , Sacramento and the San Francisco Bay Area.

The resulting method, known as the MXD method, uses a series of
equations to estimate the likely degree to which a development area’s
external traffic generation will be reduced due to development density,
diversity, design, destination accessibility, distance to transit,
demographics and development scale. UrbanFootprint uses the MXD method
and other California research on the effects of various Demand
Management strategies as its ‘8D’ travel engine.

UrbanFootprint combines the MXD estimates of trip generation by travel
mode with regional information on transportation networks and travel
distances among activities to compute measures of accessibility and
vehicle miles traveled (VMT). For consistency with regional
transportation policy and programs, UrbanFootprint draws this network
information from each MPO’s regional travel models, reflecting the
region’s Sustainable Communities Strategy (SCS) and modal emphasis
alternatives from its Regional Transportation Plan (RTP).

### How MXD Works

**Input factors**

*Land Use* (based on a half mile buffer around each location)

-   Population, Employment
-   Dwelling units by type
-   Sq. ft. of Non-residential use by category: office, retail, service,
    public

*Urban Form* (based on a half mile buffer around each location)

-   Intersection density
-   Household size
-   Auto ownership

*Location and Context*

-   Employment within 1 mile radius
-   Jobs within 30 min. by transit

**Intermediate processing** ITE trip generation rates are applied to the
land uses to calculate the maximum potential trip generation.

MXD equations are applied to calculate the likelihood of internal
capture, pedestrian, or transit use. This allows the estimation of trip
reductions based on the land use.

**Results** The reduction factors from the MXD equations are applied to
the maximum trip generation rates.

Fuel use is calculated based on a fixed fleet efficiency rate based.

### Household Costs

![image](images/AM_HouseholdCosts.png)

Based on the costs estimated per unit for energy and water use, as well
as vehicle fuel costs, total household costs are calculated.

### Public Health

![image](images/AM_PublicHealth.png)

The public health module is undergoing a major redesign at the moment.

The public health module builds on the transportation model as well as
the baseline scenario. Demographic assumptions combined with the local
environment are used to forecast the amount of time spent in moderate
and vigorous activity, proportion of the population that is overweight,
and time spent in cars. These are then used to identify the incidence of
weight and activity related diseases and resulting costs.

The transportation engine provides estimates of VMT and pollutants which
are used to estimate pedestrian-auto collisions and respiratory
illnesses, and the related costs from each.


## 6. Style Editor

The Style Editor allows the user modify the way a layer is dsiplayed on the map. A user can add new styles,
edit previously saved styles, and view the default style for the active layer's legend.

To open the Style Editor, the user can click on the layers button ![Layers Button][layers_icon] in the Layer
Management Window and select 'Layer Symbology' in the drop down.

![style_editor](images/style_editor.png)

The default style is not editable.

![style_editor_default](images/style_editor_default.png)

New styles can be added as single, categorical, or quantitative legends.

![style_editor_dropdown](images/style_editor_dropdown.png)