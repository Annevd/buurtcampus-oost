<script>
    import { onMount } from 'svelte'; 
    import Harry from '$lib/atoms/harry.svelte';
	import { text } from '@sveltejs/kit';

    // Details
    export let textTemp;
    export let name;

    // Weather
    let city = 'Amsterdam';
    let weather;

    // Harry
    let mood = 'neutraal';
    let environment = 'blij';
    let sentence = 'Ik ben even in de war';
    let detail = '';
    const numericTextTemp = parseFloat(textTemp) || 20;


    async function getWeather() {
    const res = await fetch(
        `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=52d2a223715e49a67159446b130d4482&lang=nl&units=metric`
    );
    weather = await res.json();

    const currentTemp = weather.main.temp;



    if (currentTemp > numericTextTemp + 8) {
        mood = 'blij';
        environment = 'fel';
        sentence = `Het is ${currentTemp.toFixed(1)}°C, heet!`;
        detail = ` Te warm voor de ${name}! ${numericTextTemp}°C is ideaal.`;
    } else if (currentTemp >= numericTextTemp - 5 && currentTemp <= numericTextTemp + 5) {
        mood = 'blij';
        environment = 'zonnig';
        sentence = `Het is ${currentTemp.toFixed(1)}°C, aangenaam weertje!`;
        detail = ` Bevalt de ${name} goed.`;
    } else if (currentTemp < numericTextTemp - 8) {
        mood = 'verdrietig';
        environment = 'koud';
        sentence = `Het is ${currentTemp.toFixed(1)}°C, te koud!`;
        detail = ` Te koud voor de ${name}! ${numericTextTemp}°C is ideaal.`;
    } else {
        mood = 'blij';
        environment = 'neutraal';
        sentence = `Het is ${currentTemp.toFixed(1)}°C!`;
        detail = ` Prima voor de ${name}! ${numericTextTemp}°C is ideaal.`;
    }

}

    onMount(() => {
        getWeather(); 
    });
</script>

{#if weather}
<aside>
    <div class="weather-bubble">
        <blockquote>
            “{sentence}<span class="home_page"> {detail}</span>”
        </blockquote>
    </div>
    <Harry {mood} {environment} {textTemp}/>
</aside>

{/if}
