<script>
  import { fade } from "svelte/transition";
  import { LottiePlayer } from "@lottiefiles/svelte-lottie-player";
  import { onMount } from "svelte";
  import Carousel from 'svelte-carousel';
  import Msg from './carMsg.svelte'

  let controlsLayout = [
    "previousFrame",
    "playpause",
    "stop",
    "nextFrame",
    "progress",
    "frame",
    "loop",
    "spacer",
    "background",
    "snapshot",
    "zoom",
    "info",
  ];
  let messages = [
    {
      firstP: 'To an incredible individual with great ideas, a fantastic work ethic, and a pleasure to have known and worked with.',
      secondP: 'Angello, I wish you tremendous success in the future.',
      thirdP: 'We are going to miss you!',
      sender: 'Martin M'
    },
    {
      firstP: 'Many successes in your new projects Angello!',
      secondP: 'You are a very good developer and coworker.',
      thirdP: `I'm sure you will find many SQL injections!`,
      sender: 'Jhon'
    },
    {
      firstP: 'Thanks for your hard work and professionalism!',
      secondP: 'Thanks for always maintaining a positive spirit and friendly vibes',
      thirdP: `Subscribe to SoulchipTV`,
      sender: 'Martin L'
    },
    {
      firstP: 'Thanks Angello',
      secondP: 'For all your commitment, great Energyy and passion, your goal oriented attitude and finally, your team work spirit!!',
      thirdP: `I wish you the best on your new challenges!!`,
      sender: 'Diego'
    },
    {
      firstP: 'Thank you for all you commitment with our team, for all of your incredible work and we really appreciate your hard work and friendship 😁',
      secondP: 'Wish you the best in your journey, I hope you have new adventures and challenging paths.',
      thirdP: `I really admire all of your skills, and how you are, you are a great team member and  an incredible professional`,
      sender: 'David'
    },
    {
      firstP: 'Angello, It was so great working with you, and you will be greatly missed, I hope we can cross paths again someday',
      secondP: 'Wishing you success on your new project, I am sure you will excel as you did here on GM',
      thirdP: `You are a great professional that was always ready to help, you will surely be missed`,
      sender: 'Leo'
    },
    {
      firstP: 'Angello, I am sad to see you go but I wish you the best on your next endeavors!',
      secondP: 'You were always so thorough, helpful, and present in our team meetings and I am going to miss having you there',
      thirdP: `Whoever is getting you next is lucky!`,
      sender: 'Allison'
    },
    {
      firstP: 'Even though I wished to have more chances to work with you, I can tell you are an awesome developer with great ideas',
      secondP: 'Keep those ideas coming and wish that you keep challenging and growing yourself 🙂',
      thirdP: `Hope we can have the chance to work together again!`,
      sender: 'Sergio'
    },
    {
      firstP: 'Your efforts are appreciated',
      secondP: 'Wishing you all the best for the future ahead',
      thirdP: `Thank you for being such a nice colleague 😊`,
      sender: 'Priyanka'
    },
  ]

  let showOverlay = false;
  let toggleTransparency = false;
  const timerEnd = () => {
    showOverlay = true;
    toggleTransparency = true;
  };

  onMount(() => {
    setTimeout(timerEnd, 5000);
  });
</script>

<div class="logo" class:transparency={toggleTransparency} >
  <LottiePlayer
    src="https://assets7.lottiefiles.com/private_files/lf30_rjuv1b.json"
    autoplay={true}
    loop={true}
    controls={false}
    renderer="svg"
    background="transparent"
    height={20}
    width={1920}
    {controlsLayout}
  />
</div>
{#if showOverlay}  
<div class="overlay" transition:fade>
  <h1 class="message"><span>Happy </span>Last Day!</h1>
  <Carousel
			autoplay 
			autoplayDuration={5000}
		>
    {#each messages as message}
    <Msg msg={message}/>
			{/each}
    </Carousel>
  
</div>
{/if}

<style>
  .message {
    color: white;
    font-size: 72px;
  }
  .logo {
    margin: auto;
    text-transform: uppercase;
    z-index: 1;
  }

  .transparency {
    opacity: 0.2;
  }

  .overlay {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    z-index: 2;
    height: 1000px;
  }
</style>