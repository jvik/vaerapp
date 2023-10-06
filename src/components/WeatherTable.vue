<template>
    <div class="weather-card mt-4">
        <h2>Flemsøy/Skuløy</h2>
        <div class="parameter-box">
            <div class="parameter">
                <i class="fas fa-thermometer-half"></i>
                <label>Temperatur:</label>
                <value>
                    <span id="flem-temp">{{ temperature }}</span>
                    °C
                </value>
            </div>
            <div class="parameter">
                <i class="fas fa-chart-bar"></i>
                <label>Barometer:</label>
                <value>
                    <span id="flem-pressure">1009.3</span>
                    hPa
                </value>
            </div>
        </div>
        <div class="parameter-box">
            <div class="parameter">
                <i class="fas fa-tint"></i>
                <label>Luftfuktighet:</label>
                <value>
                    <span id="flem-humidity">82</span>
                    %
                </value>
            </div>
            <div class="parameter">
                <i class="fas fa-cloud-showers-heavy"></i>
                <label>Nedbør nå:</label>
                <value>
                    <span id="flem-rain">0.24</span>
                    mm/t
                </value>
            </div>
            <div class="parameter">
                <i class="fas fa-cloud"></i>
                <label>Regn totalt i dag:</label>
                <value>
                    <span id="flem-total-rain"> 0.4</span>
                    mm
                </value>
            </div>
        </div>
        <div class="parameter-box">
            <div class="parameter">
                <i class="fas fa-wind"></i>
                <label>Vindhastighet (middelvind):</label>
                <value>
                    <span id="flem-wind-speed">13.6</span>
                    m/s
                </value>
            </div>
            <div class="parameter">
                <i class="fas fa-wind"></i>
                <label>Vindhastighet (sanntid):</label>
                <value>
                    <span id="flem-wind-speed-now">13.8</span>
                    m/s
                </value>
            </div>
            <div class="parameter">
                <i class="fas fa-compass"></i>
                <label>Vindretning:</label>
                <div>
                    <value class="wind-arrow-container" id="flem-wind-arrow-container">
                        <value class="wind-arrow" id="flem-wind-arrow">
                            <div class="wind-arrow" style="transform: rotate(104deg);">↑</div>
                        </value>
                    </value>
                </div>
            </div>
            <div class="parameter">
                <i class="fas fa-wind"></i>
                <label>Klokkslett:</label>
                <value>
                    <span id="flem-wind-gust"> {{ klokkeslett }}</span>
                    m/s
                </value>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'WeatherTable',
    props: {
        klokkeslett: String,
        temperature: String
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
    margin: 40px 0 0;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}
</style>
