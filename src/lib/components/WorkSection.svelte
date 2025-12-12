<script lang="ts">
  const events = [
    {
      name: "LIDE Brazil Investment Forum",
      desc: "Annual forum in New York connecting Brazilian companies with global investors.",
      bg: "bg-gray-100",
      img: "/generated/image-elegant-business-forum-with-ceos-and-exe-1765529536398-0.webp",
      dark: false
    },
    {
      name: "LIDE Business Dinner",
      desc: "Exclusive CEO networking events with haute cuisine and exceptional wines.",
      bg: "bg-gray-200",
      img: "/generated/image-intimate-business-dinner-with-executives-1765529539086-1.webp",
      dark: false
    },
    {
      name: "Global Conference Series",
      desc: "International forums in Tokyo, Paris, London, Dubai, and Washington.",
      bg: "bg-gray-100",
      img: "/generated/image-international-business-conference-with-d-1765529542092-2.webp",
      dark: false
    },
    {
      name: "Sectorial Forums",
      desc: "39 sector-specific forums led by industry leaders and authorities.",
      bg: "bg-gray-200",
      img: "/generated/image-business-leaders-shaking-hands-at-a-sect-1765529544521-3.webp",
      dark: false
    },
    {
      name: "Fórum Empresarial LIDE",
      desc: "Brazil's most important annual business meeting bringing together top CEOs.",
      bg: "bg-[#f0f0f0]",
      img: "/generated/image-diverse-group-of-ceos-and-business-leade-1765529546897-4.webp",
      dark: false,
      full: true
    },
    {
      name: "Prêmio Líderes do Brasil",
      desc: "Brazil's largest business award recognizing leadership excellence.",
      bg: "bg-gray-100",
      img: "/generated/image-business-executives-from-different-conti-1765529549941-5.webp",
      dark: false
    },
    {
      name: "LIDE Business Trip",
      desc: "Immersive international trips to innovative destinations for members.",
      bg: "bg-gray-200",
      img: "/generated/image-female-and-male-business-leaders-in-prof-1765529552638-6.webp",
      dark: false
    }
  ];
</script>

<section class="px-6 md:px-12 py-24 bg-white">
  <div class="max-w-3xl mb-16">
    <h2 class="text-2xl md:text-3xl font-medium leading-tight">
      <span class="font-bold">We create unparalleled opportunities for connection</span> through exclusive forums, global conferences, and strategic events that drive business growth and foster meaningful partnerships.
    </h2>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-12">
    {#each events as event}
      <div class="group cursor-pointer {event.full ? 'md:col-span-2' : ''}">
        <div class={`aspect-[4/3] w-full rounded-lg overflow-hidden relative ${event.bg} mb-4 ${event.full ? 'md:aspect-[2.5/1]' : ''}`}>
          {#if event.img}
             <img src={event.img} alt={event.name} class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105" />
          {:else}
             <!-- Placeholder for logos on solid bg -->
             <div class="w-full h-full flex items-center justify-center">
                <span class={`text-2xl font-bold ${event.dark ? 'text-white' : 'text-black'}`}>{event.name}</span>
             </div>
          {/if}
        </div>
        <h3 class="text-sm font-bold mb-1">{event.name}</h3>
        <p class="text-sm text-gray-600">{event.desc}</p>
      </div>
    {/each}
  </div>
</section>
