<script>

    import { current } from '../store.js';


    let products = [
        'Good morning','Rendez-vous', 'Never too late', 'Stargazing'
    ];

    function updatecurrent(product) {
        $current = product;
    }
</script>

<nav class="menu">
    <div class="logo">
        <img src="../src/assets/img/5p7-logo.png" alt="our logo">
    </div>
    <div class="links">
        {#each products as product}
            <p><a href="###"
                on:click="{() => updatecurrent(product)}"
                class:selected="{product === $current}">{product}</a>
            </p>
        {/each}
    </div>
</nav>