<script>

    import { current } from '../store.js';
    import { fade, scale } from 'svelte/transition';
    import { cubicOut, backOut } from 'svelte/easing';

    let products = {
        'Good morning': {
            title: 'Good morning',
            description: '<p>Wake up to the elegance of the Good Morning watch, a symbol of refined sophistication and timeless beauty.This exquisite timepiece features a pristine white dial with delicate gold accents, embodying the first light of day.</p><p>The smooth, polished case and supple leather strap offer unparalleled comfort and style, making it the perfect accessory for both business and leisure. Start your day with a touch of luxury, knowing that every moment is captured with precision and grace.</p><p>Wake up the Good Morning way.</p>',
            src: '../src/assets/img/good-morning.webp',
            info: [
                "Réf : IV7T15",
                "Weight : 127g",
                "Origin : Laos",
                "Quantity released : 2000"
            ]
        },
        'Rendez-vous': {
            title: 'Rendez-vous',
            description: '<p>Embrace the art of timekeeping with the Rendez-vous watch, a masterpiece designed for those who appreciate the finer things in life. This luxurious watch boasts a sleek, midnight blue dial adorned with sparkling diamonds, reminiscent of a starry night. The stainless steel case and bracelet provide a striking contrast, exuding strength and elegance.</p><p>Whether you\'re attending a formal event or a casual gathering, the Rendez-vous watch ensures you\'re always on time, making every encounter unforgettable.</p><p>Don\'t miss the Rendez-vous</p>',
            src: '../src/assets/img/rendez-vous.webp',
            info: [
                "Réf : 201RDV19",
                "Weight : 105g",
                "Origin : France",
                "Quantity released : 10000"
            ]
        },
        'Never too late': {
            title: 'Never too late',
            description: '<p>Defy time with the Never Too Late watch, a bold statement piece for the modern adventurer. This striking timepiece features a robust black dial with vibrant red numerals, symbolizing the urgency and passion of every second. The durable titanium case and rugged rubber strap are designed to withstand the elements, making it the perfect companion for any journey.</p><p>Embrace the spirit of adventure and seize every opportunity.</p><p>it\'s never too late to make a difference.</p>',
            src: '../src/assets/img/never-too-late.webp',
            info: [
                "Réf : N99AZ1",
                "Weight : 145g",
                "Origin : Qatar",
                "Quantity released : 250"
            ]
        },
        'Stargazing': {
            title: 'Stargazing',
            description: '<p>Capture the magic of the night sky with the Star Gazing watch, an epitome of celestial elegance.</p><p>This enchanting timepiece showcases a deep, sapphire blue dial with luminous star motifs, evoking the wonder of stargazing. The rose gold case and bracelet add a touch of warmth and luxury, creating a harmonious balance between earth and sky. Perfect for dreamers and romantics, it\'s a reminder that the universe is always within reach, one glance at a time</p>Take a break while Stargazing</p>',
            src: '../src/assets/img/stargazing.webp',
            info: [
                "Réf : A52ERT",
                "Weight : 180g",
                "Origin : Italy",
                "Quantity released : 4000"
            ]
        },
    }
</script>

<main>
    {#key products[$current].title}
        <h2 class="title" in:fade={{ duration: 300, delay: 400 }} out:fade={{ duration: 300 }} >{products[$current].title}</h2>
    {/key}
    <div class="content">
    {#key products[$current]}
        <div class="left-col">
            <img
                class="img"
                alt="{products[$current].title}"
                src="{products[$current].src}"
                in:fade={{ duration: 500, delay: 700, easing: cubicOut }}
            />
            <div class="infos"
            in:fade={{ duration: 500, delay: 200 }}>
                {#each products[$current].info as data}
                    <p>{data}</p>
                {/each}
            </div>
        </div>
        <div class="right-col">
            <p class="description"
            in:fade={{ duration: 500, delay: 700, easing: cubicOut }}   >{@html products[$current].description}</p>
            <input class="submit" type="submit" value="Order it now"
            in:scale={{ duration: 500, delay: 200, easing: backOut }}/>
        </div>
    {/key}
    </div>
</main>


