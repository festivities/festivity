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
    import {onMount} from 'svelte';

    let ready = false;
    onMount(() => ready = true);
</script>

<head>
    <title>a little festive</title>
    
    <meta property="og:title" content="festivity" />
    <meta property="og:description" content="a little festive" />
    <meta property="og:url" content="https://festivity.pw/" />
    <meta property="og:type" content="website" />
    <meta property="og:site_name" content="festivity" />
    <meta property="og:image" content="https://i.imgur.com/EPzkp45.png" />
</head>

<Splash/>

{#if ready}
    <div transition:fade="{{delay: 2750, duration: 4000, easing: circOut}}" style="display: block; justify-content: center" class="profile">
        <div class="discord_card">
            <a href="https://discord.com/users/176577264555786240"><img src="https://lanyard.cnrad.dev/api/176577264555786240?theme=light&bg=FBFBFB" alt="Festivity"></a>
        </div>
        <div class="about_me">
            <p>I make stuff. I got into programming recently <br>so here I am, lol<br><br>
			<b>contact:</b> festivity@riseup.net</p>
        </div>
        <div class="buttons">
            <a href="https://github.com/Festivize" style="text-decoration:none">
                <div class="btn">
                    GitHub
                </div>
            </a>
            <br>
            <a href="https://twitter.com/Festivizing" style="text-decoration:none">
                <div class="btn">
                    Twitter
                </div>
            </a>
            <br>
            <a href="https://www.youtube.com/c/festivityy/" style="text-decoration:none">
                <div class="btn">
                    YouTube
                </div>
            </a>
        </div>
    </div>
{/if}

<style>
    :global(body){
		background: linear-gradient(0deg, #e1e1e1, #e3e3e3, #e8e8e8, #eeeeee, #f4f4f4, #f9f9f9, #fbfbfb);
        background-size: auto;
        background-attachment: fixed;
        height: 100%;
    }
    .profile{
        position: absolute;
        left: 50%;
        top: 50%;
        transform: translate(-50%, -50%);

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

        font-family: Shippori Mincho;
        font-style: normal;
        font-weight: 400;
        font-display: swap;
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
        font-family: Shippori Mincho;
        color: #777777;
        font-size: 20px;
        padding: 10px 20px 10px 20px;
        border: solid #e1e1e1 2px;
        text-decoration: none;
    }
    .btn:hover{
        background: #FBFBFB;
        text-decoration: none;
    }
</style>