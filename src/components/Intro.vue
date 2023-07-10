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
            <h1>Intro</h1>
            <div class="col-12 col-lg-10 col-md-8 rounded-4 p-3">
                <p>
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
                    Therefore Remote Sensing we use the physical unit of REFLECTANCE (% of reflected light from 0 to 1).
                    <br> <br>

                    Nearly 10 years ago data was available in raw format and post-processed; it was necessary to be familiar
                    with the conversion formulas from RADIANCE to REFLECTANCE, elaborated on constants such as the distance
                    from the earth to the sun, the day of the year... <br>
                    In order to convert images from level 1 to level 2, more used for analysis. <br>
                    This was due to the waiting times to receive the data processed at level 2, when it was necessary to
                    process immediate analyses, the Radiance-Reflectance conversion formulas were used.
                </p>


            </div>
        </div>

    </div>
</template>


<style></style>
