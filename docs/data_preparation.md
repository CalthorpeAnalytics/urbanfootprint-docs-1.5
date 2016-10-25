# Data Preparation

## Goals

* Provide an overview of data needed by UrbanFootprint
* Describe the required fields for base data
* Walk through the steps used for SACOG’s base data preparation.
* Work through an example of preparing data for a county.

## Data Needs

UrbanFootprint is a data intensive application. The effort that goes into data collection, preparation, and review should not be underestimated.

The base data which is also called the base canvas, or existing conditions dataset will require extensive data collection, processing, and then review prior to its use. The requirements imposed by UrbanFootprint on its base conditions data include strict adherence to the data schema, and the need for a detailed understanding of the existing conditions at a parcel level. If you are working in a geographic area that has not had a prior installation of UrbanFootprint, it is unlikely that there will be a dataset that you can use without substantial effort in createing a base condition dataset.

Scenario development has looser data requirements, but will require that you have an understanding of regional and local plans for the future, and have planned out goals for the scenario that can be translated onto a map at a parcel scale.

Environmental constraint layers influence the intensity of development that is possible in locations where these constraints are present.

Reference layers provide a visual reference to UrbanFootprint users while editing or visualizing scenarios.

The transportation module (and any other modules that build on its results) will require that you have substantial additional data derived from both regional transportation infrastructure GIS as well as a travel demand model.

Some of the other analytical modules also require climate data to run.


## Data Types and Sources

### Data for the Base Canvas

| Data Type | Potential Source | Notes |
|-----------|------------------|-------|
| Cadastral/tax parcel geograpies | Tax Assessor Local Jurisdiction Regional COG/MPO |  |
| Existing land use (parcel land use codes | Tax Assessor, Local Jurisdiction, Regional COG/MPO | |
| Existing employment (2 or 4 digit NAICS codes) | Census LEHD, State or Regional COG/MPO | |
| Dwelling Units by type (parcel scale) | Tax Assessor, Local Jurisdiction, Regional COG/MPO | Parcel scale dwelling unit counts are acceptable, ideally data is provided as Single Family/MultiFamily counts |
| Population/households | Census ACS 5-Year / Other (population synthesizer etc.) | |
| Populating Age Characteristics/Educational Attainment/Household Income ranges/Race-Ethnicity/Vehicle Ownership | Census ACS 5-Year / Other (population synthesizer etc.) | |
| Parcel level Building Square Footage Data (even limited sample) | Tax Assessor, Local Jurisdiction, Regional COG/MPO | Used to calibrate building square footage estimates |
| Any aggreggate geography to be used as the unit of analysis (other than parcel) | Regional COG/MPO | |

### Data for Scenario Development

| Data Type | Potential Source | Notes |
|-----------|------------------|-------|
| Priority Development Areas | Regional COG/MPO or Local Jurisdiction | |
| Redevelopment Analysis Geographies | Regional COG/MPO or Local Jurisdiction | |
| Planned Development (in the pipeline) locations and attributes | Regional COG/MPO or Local Jurisdiction | |
| Transit Priority Zones | Regional COG/MPO or Local Jurisdiction | |
| General Plan Parcels and attributes | Regional COG/MPO or Local Jurisdiction | |
| Any existing RTP/SCS scenarios - geographies and attributes | Regional COG/MPO or Local Jurisdiction | |
| Any other existing scenarios - geographies and attributes | Regional COG/MPO or Local Jurisdiction | |
| Any other geography used to inform policy on distribution of growth | Regional COG/MPO or Local Jurisdiction | |

### Environmental Constraints

| Data Type | Potential Source | Notes |
|-----------|------------------|-------|
| Streams/Rivers | Regional COG/MPO  | |
| Wetlands | National Wetlands Inventory | |
| Vernal Pools | National Wetlands Inventory | |
| Priority Conservation Lands | Regional COG/MPO or Local Jurisdiction | |
| Slope/Digital Elevation Model (DEM) | USGS or Regional COG/MPO | |
| Flood Zones | FEMA or Regional COG/MPO | |
| Sea Level Rise Zones  |  | |
| Parks/Protected lands | CPAD Holdings | |

### Base Reference Layers

| Data Type | Potential Source | Notes |
|-----------|------------------|-------|
| County boundary(s) | Census TIGER | |
| Jurisdiction Boundaries | Local Jurisdiction | |
| Jurisdiction Sphere of Influence Boundaries | Regional COG/MPO or Local Jurisdiction | |
| Regional Sub-Area Geographies | Regional COG/MPO | |
| School/College/Universities | Regional COG/MPO, Local Jurisdiction, or Census TIGER" | |
| Health Care Facilities | Regional COG/MPO, Local Jurisdiction, or Census TIGER | |
| Public/Institutional parcels | Tax Assessor, Local Jurisdiction, Regional COG/MPO | |
| Indian Reservations/Tribal Areas | Census TIGER or Regional COG/MPO | |
| Military Areas | Census TIGER or Regional COG/MPO | |
| Open Space/Conservation Lands | Regional COG/MPO or Local Jurisdiction | |

### Transportation Data

| Data Type | Potential Source | Notes |
|-----------|------------------|-------|
| Transit stops (fixed guideway and others as available) | Regional COG/MPO or Transport District | |
| Skim Matrices for each horzon year/policy scenario | Regional MPO or Transportation Modeling Consultants | |
| Transportation network | Regional COG/MPO or Transport District | |
| Road Network (Freeways, major roads, secondary roads) | Regional COG/MPO or Transport District | |
| Street Intersection Points | Regional COG/MPO or Transport District | |
| Railroads: light rail, commuter rail, and selected freight rail | Regional COG/MPO or Transport District | |
| TAZ geography(s) | Regional COG/MPO or Transport District | |
| Bike network (if available) | Regional COG/MPO or Transport District | |
| Sidewalks (if available) | Regional COG/MPO or Transport District | |

### Analysis Reference Data

| Data Type | Potential Source | Notes |
|-----------|------------------|-------|
| Climate Zones (for energy modeling) | | |
| Evapotranspiration Zones (for outdoor water modeling) | | |

## Base Data Schema: SACOG

* The structure and field names are critical.
* There is a single table
* Which will be uploaded to PostGIS
* For convenience the discussion of fields will be divided into groups

 * Metadata and Geography
 * Paint Configuration
 * Parcel Areas/Types
 * Residential/Housing
 * Employment
 * Building Square footage
 * Outdoor Irrigated Area

### Metadata and Geography

| Field Name | Description |
|------------|-------------|
|id | UF unique id |
|geography_id | original geometry id (from SACOG) |
|wkb_geometry | PostGreSQL geometry field (will not be visible in ArcGIS) |
|region_lu_code | SACOG land use code |
|built_form_key | identifier (name of) for building  type or place type key |
|created | date of data creation/import into UF system |
|updated | date of data change or modifiction within UF system |

### Paint Configuration

These fields are not used in the base features dataset, but are included to maintain an identical structure to the End State data.

| Field Name | Description |
|------------|-------------|
| dev_pct | development percent - proportion of geography receiving building type or place type application |
| density_pct density percent | proportional intensity of building type or place type application |
| gross_net_pct gross-to-net percent | proportion of developed acreage that receives building type or place type application |
| clear_base_flag | boolean field to indicate clearance of development program (removal of all base year dwelling units and employees) |
| redevelopment_flag | boolean field to indicate/track redevelopment on geography |
| dirty_flag | used internally by UF during paint application |


### Parcel Area/Type

| Field Name | Description |
|------------|-------------|
| intersection_density_sqmi | density of walkable street intersections in the geography (calculated as a weighted square mile density) |
| acres_gross | gross/total acreage of the geography |
| acres_parcel |  gross/total acreage of the parcel(s) |
| sqft_parcel | parcel square footage |
| acres_parcel_res |  residential acreage of the parcel |
| acres_parcel_res_detsf_sl | acreage of parcel with single family small lot detached homes (<5500sf) |
| acres_parcel_res_detsf_ll | acreage of parcel with single family large lot detached homes (>5500sf) |
| acres_parcel_res_attsf |  acreage of parcel with single family attached homes/townhomes |
| acres_parcel_res_mf | acreage of parcel with multifamily housing |
| acres_parcel_emp |  acreage of parcel with employment |
| acres_parcel_emp_off |  acreage of parcel with office employment |
| acres_parcel_emp_ret |  acreage of parcel with retail employment |
| acres_parcel_emp_ind |  acreage of parcel with industrial employment |
| acres_parcel_emp_ag | acreage of parcel with agricultural employment |
| acres_parcel_emp_mixed |  acreage of parcel with mixed employment uses |
| acres_parcel_emp_military | acreage of parcel with military employment |
| acres_parcel_mixed |  acreage of parcel with mixed use (residential and employment) |
| acres_parcel_mixed_w_off |  acreage of mixed use parcels with residential and employment (includes office employment) |
| acres_parcel_mixed_no_off | acreage of mixed use parcels with residential and employment (no office employment |
| acres_parcel_no_use | acreage of parcel with no use |

### Residential and Housing

| Field Name | Description |
|------------|-------------|
| hh | households |
| du | dwelling units |
| du_detsf | detached single family dwelling units |
| du_detsf_sl | detached single family small lot dwelling units |
| du_detsf_ll | detached single family large lot dwelling units |
| du_attsf | attached single family dwelling units |
| du_mf | multifamily dwelling units |
| du_mf2to4 | units in multifamily buildings with 2 to 4 dwelling units |
| du_mf5p | units in multifamily buildings with 5 or more dwelling units |

### Employment

| Field Name | Description |
|------------|-------------|
| emp | number of employees |
| emp_ret | number of retail employees |
| emp_retail_services | number of retail services employees |
| emp_restaurant | number of restaurant employees |
| emp_accommodation | number of accommodation employees |
| emp_arts_entertainment | number of arts and entertainment employees |
| emp_other_services | number of other services employees |
| emp_off | number of office employees |
| emp_office_services | number of office services employees |
| emp_public_admin | number of public administration employees |
| emp_education | number of education employees |
| emp_medical_services | number of medical services employees |
| emp_ind | number of industrial employees |
| emp_manufacturing | number of manufacturing employees |
| emp_wholesale | number of wholesale employees |
| emp_transport_warehousing | number of transportation and warehousing employees |
| emp_utilities | number of utilities employees |
| emp_construction | number of construction employees |
| emp_ag | number of agricultural/extration employees |
| emp_agriculture | number of agricultural employees |
| emp_extraction | number of extraction employees |
| emp_military | number of military employees |

### Building Square Footage

| Field Name | Description |
|------------|-------------|
| bldg_sqft_detsf_sl | building square footage of detached single family small lot homes |
| bldg_sqft_detsf_ll | building square footage of detached single family large lot homes |
| bldg_sqft_attsf | building square footage of attached single family homes/townhomes |
| bldg_sqft_mf | building square footage of multifamily units |
| bldg_sqft_retail_services | building square footage of retail services  |
| bldg_sqft_restaurant | building square footage of restaurants |
| bldg_sqft_accommodation | building square footage of accommodation |
| bldg_sqft_arts_entertainment | building square footage of arts and entertainment |
| bldg_sqft_other_services | building square footage of other services |
| bldg_sqft_office_services | building square footage of office services |
| bldg_sqft_public_admin | building square footage of public administration |
| bldg_sqft_education | building square footage of education |
| bldg_sqft_medical_services | building square footage of medical services |
| bldg_sqft_transport_warehousing | building square footage of transportation and warehousing |
| bldg_sqft_wholesale | building square footage of wholesale |

### Outdoor Irrigated Area

| Field Name | Description |
|------------|-------------|
| residential_irrigated_sqft | residential outdoor irrigated square feet |
| commercial_irrigated_sqft | commercial outdoor irrigated square feet |

## Base Data Preparation: SACOG

#### Input Data

* SACOG parcel data
    * SACOG Land Use
    * Dwelling Units
* SACOG TAZ
    * Census 2010 Blockgroups
    * Census 2010 Tracts

### Data Preparation: Topology

* Parcels must not overlap
* Clip the dataset to the county border
* Remove roads and waterbodies

### Dwelling Units

| SACOG Use Code | Dwelling Unit Type |
|----------------|--------------------|
| Rural Residential | Single Family |
| Farm Home | Single Family |
| Very Low Density Res. | Single Family |
| Low Density Res. | Single Family |
| Large Lot Not Farm Home | Single Family |
| Medium Density Res. | Multifamily |
| Medium-High Density Res. | Multifamily |
| High Density Res | Multifamily |
| Urban Residential | Multifamily |

* Total DU = SACOG Parcel DU
* Controlled to TAZ totals
* Assign DU type using crosswalk (right), and assign DU totals to du_detsf
* Du_detsf_sl and du_detsf_ll based on sf/du calculation.
* ACS rates for Attached SF, MF 2-4, and MF 5 plus are applied to all parcels with MF units

### Households

* HH from SACOG 2008
* DU from Parcel Data
* Occupancy rate = HH/DU

### Population

* Calculate Average HH by block group from census data
* Ave. HH size = pop/hh
* Then multiply the HH count in each parcel by the Ave. HH size.

### Employment

* Parcel employment from SACOG 2008
* Crosswalk using the table
* Use LEHD to disaggregate where needed. (next page)
* Accommodation extracted using SACOG Employment Inventory

**Employment Land Use Crosswalk**

| SACOG Category | UrbanFootprint Employment Category |
|----------------|------------------------------------|
| EmpGov | Emp_Public_admin |
| EmpOfc | Emp_Office_services |
| EmpMed | Emp_Medical_services |
| EmpEdu | Emp_Education |
| EmpRet | Emp_Retail_services |
| EmpFood | Emp_Restaurant |
| EmpSvc | Emp_Entrec, Emp_Othe_services, Emp_Accomodation |
| EmpInd | Emp_Utilities, Emp_Transware, Emp_Warehouse, Emp_Wholesale, Emp_Construction, Emp_Manufacturing, Emp_Agriculture, Emp_Extract |
| EmpOth | Emp_military |

### Employment Processing and Source

**Employment Processing and Source**

| UF Employment Sub Category | Method for Spatially Deriving Field at Parcel | SACSIM Category |
|----------------------------|-----------------------------------------------|-----------------|
| Emp_Public |  ,Direct Crosswalk from SACSIM Category | EmpGov |
| Emp_Office | Direct Crosswalk from SACSIM Category | EmpOfc |
| Emp_Medss | Direct Crosswalk from SACSIM Category | EmpMed |
| Emp_Educ | Direct Crosswalk from SACSIM Category | EmpEdu |
| Emp_Retail | Direct Crosswalk from SACSIM Category | EmpRet |
| Emp_Restaurant | Direct Crosswalk from SACSIM Category | EmpFood |
| Emp_Entrec | LEHD 2010 Near Imputed Rate (Block) | EmpSvc |
| Emp_Other | LEHD 2010 Near Imputed Rate (Block) | EmpSvc |
| Emp_Accommodation | SACOG Employment Inventory | EmpSvc |
| Emp_Transware | LEHD 2010 Near Imputed Rate (Block) | EmpInd |
| Emp_Warehouse | LEHD 2010 Near Imputed Rate (Block) | EmpInd |
| Emp_Whole | LEHD 2010 Near Imputed Rate (Block) | EmpInd |
| Emp_Constr | LEHD 2010 Near Imputed Rate (Block) | EmpInd |
| Emp_Manuf | LEHD 2010 Near Imputed Rate (Block) | EmpInd |
| Emp_Agriculture | LEHD 2010 Near Imputed Rate (Block) | EmpInd |
| Emp_Extract | LEHD 2010 Near Imputed Rate (Block) | EmpInd |
| Emp_AF | Direct Crosswalk from SACSIM Category | EmpOth |


Disaggregation
______________

* This technique is used several times during data preparation.
* Calculate the proportion of each SACOG category that goes into each UF Employment Category.
* Use the LEHD 2010 near imputed rate datase as the basis for the disaggregation.

i.e. %emp_entrec = 100*emp_entrec/
(emp_entrec+emp_other_services+emp_accomodation)


Dataset 1 (higher accuracy): 95 employees

Dataset 2: 50 retail, 30 service, and 20 industrial employees.

+---------+------+------+------+------+------+-----+
|Total Emp|Ret. %|Ser. %|Ind. %|# Ret.|# Ser.|# Ind|
+=========+======+======+======+======+======+=====+
|95       |50  |30  |20    |47.5  |28.5  |19   |
+---------+------+------+------+------+------+-----+


Concerns: Zeros and Nulls

Building Square Footage
_______________________

Need info

Irrigated Square Footage
________________________

Need info

Developablity
_____________

Need info

### Keep the Goal in Mind

* Data for your region will be unique
* This process should serve as a starting point for developing your data, not a fixed recipe.
