<script>
	import { page } from "$app/stores";
    import "../app.css";
    import LocomotiveScrollProvider from 'svelte-locomotive-scroll'
</script>
  
<LocomotiveScrollProvider
    options={{
        smooth: true
    }}
    watch={[
        $page
    ]}
    location={$page.url}
    onLocationChange={(scroll) => scroll.scrollTo(0, { duration: 2, disableLerp: false })}
    imageTarget={''}
>
    <slot />
</LocomotiveScrollProvider>