<script>
    export let data;
	import { HeroHeaders, Dot } from '$lib/index.js';

</script>

<HeroHeaders 
    heroInfo="{data.heroHeaders[2]}"
/>

<section>
    <article>
        <div>
            <Dot svgFill="var(--main-color-green)"/>
            <h2>
                Maak Amsterdam <span>Groener</span> 
            </h2>
        </div>
        <ul>
            <li><b>Verfraait de straat:</b> Geveltuinen zorgen voor kleur en leven in de brouwerij.</li>
            <li><b>Goed voor het milieu:</b> Planten in geveltuinen nemen CO2 op en zorgen voor een schonere lucht. Ze filteren ook fijnstof en regenwater.</li>
            <li><b>Koeler in de zomer:</b> Planten in geveltuinen zorgen voor schaduw en verdampen water, wat voor een verkoelend effect zorgt in de stad.</li>
            <li><b>Goed voor de biodiversiteit:</b> Geveltuinen bieden nectar en stuifmeel voor insecten zoals bijen en vlinders.</li>
            <li><b>Gezellig:</b> Geveltuinen zorgen voor een meer sociale en betrokken buurt.</li>
        </ul>
    </article>
    <picture>
        <img  width="583" height="682" loading="lazy" src="/assets/geveltuin-card.webp" alt="Geveltuin" />
    </picture>
</section>

<style>
    section{
        display: grid;
        flex-direction: column;
        background-color: var(--main-color-beige);
        border-radius: var(--border-card);
        height: 100%;
        width: 100%;
        top: -1em;
        position: relative;
        padding: 1em 1.5em;
        overflow: hidden;
        font-family: var(--sub-header-font);
    }

    section::after{
        content: url(/assets/leaf-orange.svg);
        width: 17em;
        height: 17em;
        opacity: 0.5;
        position: absolute;
        right: -3em;
        top: -3em;
        transform: rotate(-45deg);
    }
    article{
        display: flex;
        flex-direction: column;
        align-items: center;
        position: relative;
        background-color: var(--main-color-beige);
        border-radius: var(--border-bigCard);
        width: 100%;
    }

    article > div{
        display: flex;
        gap: .5em;
        width: 100%;
    }
    h2{
        font-family: var(--header-font);
        font-size: 2.5em;
        line-height: 95%;
        max-width: 7em;
        color: var(--main-color-brown);
        z-index: 1;
    }
    h2 span{
        color: var(--main-color-green);
    }
    picture{
        display: flex;
        justify-content: start;
        max-width: 35em;
        min-width: 13em;
        margin: 2em 5.5em;
        overflow: hidden;
        min-height: 16em;
        border-radius: var(--border-bigCard);
    }
    img{
        display: flex;
        justify-content: center;
        border-radius: var(--border-bigCard);
        width: 100%;
        height: 100%;
        z-index: 1;
    }

    article ul {
        font-family: 'Poppins-Regular';
        color: var(--main-color-brown);
        margin: 2em 3.5em;
        list-style-image: url("/assets/circle-green.svg");
        font-size: 1em;
    }

    article ul li{
        padding-left: .5em;
    }
    ul b{
        font-family: 'Poppins-Bold';
    }

    /* MEDIA QUERY Small Tablet = 500px */
    @media (min-width: 31rem) {
        section{
            width: 90%;
            margin: 0 auto;
        }

    }

    /* MEDIA QUERY TABLET = 768px */
    @media (min-width: 48rem) {
        section{
            width: 97%;
            padding: 3.5em 2em 1em 5em;
            grid-template-columns: 1fr 1fr;
            grid-template-areas: 
                'blok1 blok2'
                'blok1 blok2';
            grid-area: blok1;
            gap: 0 5em;
        }
        section::after{
            width: 23em;
            left: -3em;
            top: -2em;
            transform: rotate(70deg);
        }
        picture{
            height: 95%;
            grid-area: blok2;
            width: 96%;
            margin: 0;
        }
        h2{
            font-size: 4em;
            margin-bottom: .2em;
        }

        ul{
            margin: 2em 0;
            width: 64%;
        }
    }
</style>

