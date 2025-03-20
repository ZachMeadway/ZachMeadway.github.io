<script>
    import { PrismicLink } from '@prismicio/svelte';
import WordMark from './WordMark.svelte';

    /** @type {import("@prismicio/client").Content.SettingsDocument} */
    export let settings;



</script>



<footer>
    <nav>
        <a href="/">
            <WordMark />
            <span class="sr-only">{settings?.data?.site_title || 'Default Title'} home page</span>
        </a>
        
        <ul>
            {#each settings.data.navigation as item (item.label)}
            <li>
                <PrismicLink field={item.link}>
                    {item.label}
                </PrismicLink>
            </li>
            {/each}
        </ul>
    </nav>
</footer>