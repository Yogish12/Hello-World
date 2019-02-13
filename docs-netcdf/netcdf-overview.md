**Yara Digital Farming Platform**

**NetCDF (.nc) Files**

*Author: Yara Digital Farming Platform Team*

*Owner: IBM Global Business Services*

[1 Document Overview 4](#document-overview)

[1.1 Document Audience 4](#document-audience)

[2 Functional Requirement 4](#functional-requirement)

[3 NetCDF Overview 5](#netcdf-overview)

[3.1 NetCDF File Structure 6](#netcdf-file-structure)

[3.2 NetCDF Data Model - Classic 6](#netcdf-data-model---classic)

[3.3 NetCDF Enhanced Model 7](#netcdf-enhanced-model)

[4 CSC NetCDF file examples and APIs
8](#csc-netcdf-file-examples-and-apis)

[4.1 C3S-SOILMOISTURE-L3S-SSMV-COMBINED-DEKADAL
8](#c3s-soilmoisture-l3s-ssmv-combined-dekadal)

[4.2 C3S\_OZONE-L3-06TC-IASI\_METOPB 8](#c3s_ozone-l3-06tc-iasi_metopb)

**Document History**


This is a snapshot of an on-line document. Paper copies are valid only
on the day they are printed. Refer to the author if you are in any doubt
about the currency of this document.

[]{#TDocumentSource .anchor}

[]{#TRevisionHistory .anchor}

**Revision History**

  V0.1                                              08/02/2019                                    First Draft

Document Overview
=================

This document provides high level overview of **Network Common Data
Form** (NetCDF) format of Meteorological data from various Satellites.
NetCDF is an open standard and 64 bit offset format are an International
Standard of Open Geospatial Consortium. NetCDF files typically follow
the Common Data Model for Scientific Data Sets with 3 layers.

1.  Data Access Layer: Also known as the syntactic layer, handles Data
    reading

2.  Coordinate System Layer: Identifies the coordinates of the data
    arrays. Coordinates are a completely general concept for scientific
    data; specialized georeferencing coordinate systems are specially
    annotated.

3.  Scientific Data Layer: Identifies specific types of data such a
    grids, images, and point data and adds specialized method for each
    kind of data.

    Further details about NetCDF can be found here
    <https://www.unidata.ucar.edu/software/netcdf/docs/faq.html>

Document Audience
-----------------

The primary audience includes:

-   Data Architects

-   Data Engineers

-   Data Scientists

-   Developers

These are the individuals who have the responsibility for envisioning,
modeling, and structuring the data services and data pipelines for
Yara Digital Farming Platform.

Functional Requirement
======================

-   Understand Format, Structure, Schema and processing NetCDF files
    with Satellite Data and images.

-   Models for

    -   Ingestion

    -   Raw

    -   Conformed/User layers

NetCDF Overview
===============

The Network Common Data Form, or netCDF, is an interface to a library of
data access functions for storing and retrieving data in the form of
arrays. An array is an n-dimensional (where n is 0, 1, 2, ...)
rectangular structure containing items which all have the same data type
(e.g., 8-bit character, 32-bit integer). A scalar (simple single value)
is a 0-dimensional array.

NetCDF is an abstraction that supports a view of data as a collection of
self-describing, portable objects that can be accessed through a simple
interface. Array values may be accessed directly, without knowing
details of how the data are stored. Auxiliary information about the
data, such as what units are used, may be stored with the data. Generic
utilities and application programs can access netCDF datasets and
transform, combine, analyze, or display specified fields of the data.
The development of such applications has led to improved accessibility
of data and improved re-usability of software for array-oriented data
management, analysis, and display.

NetCDF File Structure
---------------------

A netCDF classic dataset (including CDF-1, 2, and 5 formats) is stored
as a single file comprising two parts:

-   a header, containing all the information about dimensions,
    attributes, and variables except for the variable data;

-   a data part, comprising fixed-size data, containing the data for
    variables that don't have an unlimited dimension; and variable-size
    data, containing the data for variables that have an unlimited
    dimension.

Both the header and data parts are represented in a machine-independent
form. This form is very similar to XDR (eXternal Data Representation),
extended to support efficient storage of arrays of non-byte data.

NetCDF Data Model - Classic
---------------------------

> The data model of dimensions, variables, and attributes, which define [The Classic
> Model](https://www.unidata.ucar.edu/software/netcdf/docs/netcdf_data_model.html#classic_model),
> was extended starting with netCDF-4.0.
>
> ![](./img/media/image1.png){width="5.355555555555555in"
> height="3.8862095363079616in"}

NetCDF Enhanced Model
---------------------

> The new [Enhanced Data
> Model](https://www.unidata.ucar.edu/software/netcdf/docs/netcdf_data_model.html#enhanced_model)
> supports the classic model in a completely backward-compatible way,
> while allowing access to new features such as groups, multiple
> unlimited dimensions, and new types, including user-defined types.

![](./img/media/image2.png){width="5.971185476815398in"
height="3.8296292650918633in"}

CSC NetCDF file examples and APIs
=================================

> Further analysis is required to extract Schema and Data from the .nc
> (extension for NetCDF) files, by building a Utility in Python.
> Satellite Data from Copernicus Climate Change Services (C3S)
> implemented by ECMWF Provides Long term observations for Glaciers
> elevation, Leaf area index, Sea Level Gridded Data, CO2 Data, Methane
> Data, Seasonal Forecast, Soil Moisture Data etc. The .nc files are in
> Hierarchical Data Format (HDF). The data can be downloaded via APIs.
>
> HDF structure example:
>
> ![](./img/media/image3.png){width="6.5in"
> height="3.4340277777777777in"}

C3S-SOILMOISTURE-L3S-SSMV-COMBINED-DEKADAL
-------------------------------------------

<https://ibm.box.com/s/s96m94iibhak9grfeh2zczw6z2jzkahb>

C3S\_OZONE-L3-06TC-IASI\_METOPB
-------------------------------

<https://ibm.box.com/s/w5pvlu86at1i09hgusvkdrvbfd6hqjkt>
