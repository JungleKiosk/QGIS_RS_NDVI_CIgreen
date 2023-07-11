<script>

export default {
    data() {
        return {

        };
    }
}

</script>

<template>
    <section id="jumbo" >
        <div class="container opacity">
            <div class="row">
                <div class="col-12 col-lg-10 col-md-8 rounded-4 p-3">
                    <div class="txt_p">
                        <p>
                            This project aims to start an Remote Sensing analysis and to provide an intuitive workflow to download high resolution satellite images from
                            the
                            <a href="https://earthexplorer.usgs.gov/">
                                USGS (United States Geological Survey)</a> website, process them and calculate the NDVI and
                            CIgreen
                            vegetation indices. <br> <br>
                        </p>
                    </div>
                </div>
            </div>
    
        </div>
    </section>
</template>


<style>

#jumbo {
    background-image: url('../assets/img/jumbo.png');
    background-size: cover;
    background-repeat: no-repeat;
}

.txt_p {
    position: relative;
    z-index: 1;
}

#jumbo::before {
    content: '';
    position: absolute;
    top: 50;
    left: 0;
    width: 100%;
    height: 20.9%;
    background-color: rgba(0, 0, 0, 0.6); /* Imposta qui l'opacità desiderata */
}

</style>
