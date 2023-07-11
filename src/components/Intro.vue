<script>

export default {
    data() {
        return {

        };
    }
}

</script>

<template>
    <div class="container my-5">
        <div class="row">
            <div class="col-12 col-lg-10 col-md-8 rounded-4 p-3">

                <p>
                <h4>Intro:</h4>
                the USGS policy is to keep data processed with obsolete and newer technologies on file (obsolescence
                time: 4-5 years); this makes it useful for those contexts in which it is necessary to compare data with
                different acquisition characteristics, a key issue for the analysis of multi-time series (main
                advantages of RS). <br>
                Therefore, it is essential to understand the type of data to be analyzed, in order to avoid errors of
                interpretation. The data is divided into levels:
                </p>

                <ul>
                    <li>level 0</li>
                    <li>level 1</li>
                    <li>level 2</li>
                </ul>

                <p>
                    the higher the level, the higher the processing accuracy. <br> <br>
                    The raw data taken from the satellite is NOT a physical unit but a numeric one, each pixel corresponds
                    to a
                    Digital Number (DN) numeric value, meaningless to the user for purposes of geospatial interpretation
                    (level
                    0:
                    this data is often not distributed). <br> <br>
                    Level 1 data is usually distributed, whose DN is processed in physical value of
                    <a href="https://www.usgs.gov/landsat-missions/using-usgs-landsat-level-1-data-product">RADIANCE</a>
                    (amount of
                    radiation reflected by a single pixel), however it is not a comparable measure between various images
                    because it depends a lot on the position of the sun, of the satellite to a certain pixel...
                    Therefore Remote Sensing (RS) we use the physical unit of REFLECTANCE (% of reflected light from 0 to
                    1).
                    <br> <br>

                    Nearly 10 years ago data was available in raw format and post-processed; it was necessary to be familiar
                    with the conversion formulas from RADIANCE to REFLECTANCE, elaborated on constants such as the distance
                    from the earth to the sun, the day of the year... <br>
                    In order to convert images from level 1 to level 2, more used for analysis. <br>
                    This was due to the waiting times to receive the data processed at level 2, when it was necessary to
                    process immediate analyses, the Radiance-Reflectance conversion formulas were used. <br> <br>

                    To date the data are already processed ready to use and are available in collection 2, the contexts of
                    analysis in which it is necessary to exploit the conversion formulas are rare. <br>
                    In addition, level 2 data includes atmospheric corrections (the last link of the pre-processing); the
                    atmosphere has an effect on the radiation and alters the spectral signatures, indices and various
                    processings. The effect is not completely eliminated but greatly reduced. <br> <br>

                    Data can also be used without atm corrections: comparison between sensors of different constellations_
                    eg: landsat vs sentinel: using atmospherically corrected data could cause errors, because the data
                    correction methods are different and there could be some inconsistencies in the comparison.

                <h4>Image Choice Concepts:</h4>
                For an analysis of the vegetation, snow represents a covering element, therefore to be avoided. <br>
                The NIR, NIR-1, RED configuration (thanks to the fact that there is mid-infrared) allows you to identify
                snow (cyan color) and distinguish it from clouds (white color). <br>
                The visual coverage for the RS is the main problem, it may happen that even the clouds are of cyan colour,
                this is because the phenomenon of surface freezing of the clouds occurs especially in winter. <br>
                Another important aspect to consider is the shading by the clouds on the surface, influencing the quality of
                the data collected. <br> <br>
                So the first phase of vegetation analysis is the search for clean images, without coverage. <br> <br>
                Finding optical images suitable for your analysis purposes is not obvious.
                It may happen that the territory under examination was covered by clouds, cirrus clouds, snow, shadows,
                which would have caused an error in the estimation of the spectral signature values. <br>
                Also, for the same reason, the research archive may not be unique; in fact, I had to download from the USGS,
                images belonging to the Landsat5 and Landsat8 archive.
                Before using the data, it is necessary to apply a surface reflectance scale factor to each pixel of each
                band, to transform the reflectance values into absolute physical values of radiance to the sensor
                (Pre-processing); <br> <br>

                <h4>Spectral signature: </h4>

                Landsat 7 has an onboard EMT sensor while Landsat4-5 had EMT, avoid L7 data because only for a few years the
                sensor has been damaged. To view a satellite image you must choose the correct combination of bands with
                respect to RGB (Red Green Blue), consequently adapt the combination according to the satellite sensor from
                which the data are
                acquired. <br> <br>

                <img src="../assets/img/spectral_signatures.png" alt=""> <br> <br>

                Display with RGB combination: <br>
                Landsat7 = B3, B2, B1 <br>
                Landsat8 = B4, B3, B2 <br> <br>

                Snow display: <br>
                Landsat7 = B5 (NIR-1 mid-IR), B4, B3 <br>
                Landsat8 = B6 (NIR-1 mid-IR), B5, B4 <br> <br>

                Cloud display: <br>
                Landsat7 = B4, B3, B2 (NIR, red, green) <br>
                Landsat8 = B5, B4, B3 (NIR, red, green) <br> <br>

                <img class="img" src="../assets/img/comb_bands.png" alt=""> <br>
                <a href="https://www.usgs.gov/media/images/common-landsat-band-combinations">USGS web site</a> <br> <br>

                <h4>Vegetation indices: </h4>
                Calculation of vegetation indices is a widely used method for assessing vegetation health and density using
                satellite imagery. One of the most common vegetation index is the
                <a href="https://www.usgs.gov/landsat-missions/landsat-normalized-difference-vegetation-index">Normalized
                    Difference Vegetation Index</a> (NDVI),
                usually used for analysis contexts where the vegetation is moderately dense. <br> <br>

                The relationship between NDVI and LAI (Leaf Area Index) is logarithmic: at high LAI values ( > 4 ) the function
                tends to saturate and the index becomes insensitive to high densities of vegetation, while the
                relationship between
                <a href="Green Chlorophyll Index">Green Chlorophyll Index</a> (CIgreen)
                and LAI is linear. <br>
                In an analysis context in which the vegetation is very dense, the CIgreen index better discretizes the
                different zones of vegetal vigor.
                <br> <br>

                <div class="row">
                    <div class="col-12 col-lg-6">
                        <h5>NDVI</h5>
                        <img src="../assets/img/index_NDVI.png" alt="">
                    </div>
                    <div class="col-12 col-lg-6">
                        <h5>CIgreen</h5>
                        <img src="../assets/img/index_CIgreen.png" alt="">
                    </div>
                </div>

                </p>

            </div>
        </div>

    </div>
</template>


<style>
.img {
    width: 60%;
}

a {
    color: #f2b91e;
}
</style>
