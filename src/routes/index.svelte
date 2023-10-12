<script>
    // global files
    import css from '../styles/global.css';

    // external modules
    import Parallax from 'parallax-js'

    // other components
    import Splash from '../components/splash.svelte';

    // transitions
    import {fade} from 'svelte/transition';

    // easing functions
    import {circOut} from 'svelte/easing';

    // things i copy pasted
    import {onMount, tick} from 'svelte';

    let ready = false;
    let parallaxInstance;
    let backgroundparallaxInstance;
    let backgroundMusic;

    onMount(async() => {
        ready = true;
        await tick();

        const scene = document.getElementById('scene');
        const background = document.getElementById('background');
        parallaxInstance = new Parallax(scene);
        backgroundparallaxInstance = new Parallax(background);

        backgroundMusic = new Audio('https://github.com/festivize/festivity/blob/main/static/background.ogg?raw=true');
        backgroundMusic.volume = 0.1; backgroundMusic.loop = true; backgroundMusic.play();
    });
</script>

<head>
    <title>a little festive</title>
    
    <meta property="og:title" content="festivity" />
    <meta property="og:description" content="a little festive" />
    <meta property="og:url" content="https://festivity.codes/" />
    <meta property="og:type" content="website" />
    <meta property="og:site_name" content="festivity" />
    <meta property="og:image" content="https://i.imgur.com/EPzkp45.png" />
</head>

<Splash/>

{#if ready}
    <div id="background" transition:fade="{{delay: 2750, duration: 4000, easing: circOut}}" class="parallax">
        <div data-depth="0.05" class="bg"></div>
    </div>
    <div id="scene" transition:fade="{{delay: 2750, duration: 4000, easing: circOut}}" class="parallax">
        <div data-depth="0.2" class="profile">
            <div class="discord_card">
                <a href="https://discord.com/users/176577264555786240"><img src="https://lanyard.cnrad.dev/api/176577264555786240?theme=light&bg=FBFBFB&hideDiscrim=true" alt="festivity"></a>
            </div>
            <div class="about_me">
                <p>An artist, a programmer ————<br>a student with insatiable curiosity.<br><br>
                <b>Contact:</b> festivizing@gmail.com</p>
            </div>
            <div class="buttons">
                <a href="https://github.com/festivities" target="_blank" style="text-decoration:none">
                    <div class="btn">
                        GitHub
                    </div>
                </a>
                <br>
                <a href="https://twitter.com/festivizing" target="_blank" style="text-decoration:none">
                    <div class="btn">
                        Twitter
                    </div>
                </a>
                <br>
                <a href="https://festivity.carrd.co/" target="_blank" style="text-decoration:none">
                    <div class="btn">
                        Carrd
                    </div>
                </a>
            </div>
        </div>
    </div>
{/if}

<style>
    :global(body){
		background: linear-gradient(0deg, #e1e1e1, #e3e3e3, #e8e8e8, #eeeeee, #f4f4f4, #f9f9f9, #fbfbfb);
        background-size: auto;
        background-attachment: fixed;
        height: 100%;
        overflow: hidden;
    }
    .bg{
        height: 150vh !important;
        background: linear-gradient(0deg, #e1e1e1, #e3e3e3, #e8e8e8, #eeeeee, #f4f4f4, #f9f9f9, #fbfbfb);   
        content: url("https://raw.githubusercontent.com/festivize/festivity/main/static/background.webp") !important;
        filter: grayscale(50%);
        opacity: 0.5;
    }
    .parallax{
        display: block;
        justify-content: center;
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%) !important;
    }
    .profile{
        position: relative !important;
        left: -80% !important;
        top: 50% !important;
        background-color: #FBFBFB;
		animation: float 2.7s infinite;
		box-shadow: 0px 20px 20px rgba(56, 56, 56, 0.306);
		border-radius: 20px;
    }
    .discord_card{
        pointer-events: none;
    }
    .about_me{
        border-top: 3px dashed #e1e1e1;

        display: block;
        text-align: justify;
        padding: 20px;

        color: #777777;

        font-family: 'Inter Tight', sans-serif;
        font-style: normal;
        font-weight: 400;
        font-display: swap;
        letter-spacing: 0.04em;
    }
    .buttons{
        border-top: 3px dashed #e1e1e1;
        padding: 20px;
    }
    .btn{
        margin: auto;
        text-align: center;
        background-image: linear-gradient(to bottom, #FBFBFB, #F5F5F5);
        border-radius: 4px;
        font-family: 'Inter Tight', sans-serif;
        color: #777777;
        font-size: 20px;
        padding: 10px 20px 10px 20px;
        border: solid #e1e1e1 2px;
        text-decoration: none;
        letter-spacing: 0.04em;
        font-weight: 400;
        pointer-events: auto !important;
    }
    .btn:hover{
        background: #FBFBFB;
        text-decoration: none;
    }

    @media only screen and (max-width: 767px){
    .profile{
        left: 0% !important;
        top: 50% !important;
    }
  }
</style>
