<script lang="ts">
  const cards = [
    {
      title: "We're Not Just a Network...",
      subtitle: "We're a Global Movement.",
      image: "/generated/image-diverse-group-of-ceos-and-business-leade-1765529546897-4.webp"
    },
    {
      title: "We Don't Just Connect People...",
      subtitle: "We Create Lasting Partnerships.",
      image: "/generated/image-business-executives-from-different-conti-1765529549941-5.webp"
    },
    {
      title: "We Don't Just Host Events...",
      subtitle: "We Shape Economic Future.",
      image: "/generated/image-female-and-male-business-leaders-in-prof-1765529552638-6.webp"
    }
  ];
</script>

<section class="py-24 px-6 md:px-12 bg-white">
  <div class="max-w-2xl mb-16">
    <p class="text-xl md:text-2xl leading-relaxed text-gray-800">
      LIDE isn't just about networking—it's about building trusted relationships that drive real business outcomes. We unite and connect leaders to foster business and legacies, contributing to the socioeconomic development of nations.
    </p>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
    {#each cards as card}
      <div class="group">
        <div class="aspect-[4/3] overflow-hidden rounded-lg mb-4 bg-gray-100">
          <img src={card.image} alt={card.title} class="w-full h-full object-cover grayscale group-hover:grayscale-0 transition-all duration-500" />
        </div>
        <h3 class="text-sm text-gray-500 mb-1">{card.title}</h3>
        <p class="text-sm font-bold">{card.subtitle}</p>
        
        <div class="flex justify-between mt-4 text-xs text-gray-400">
           <span>01</span>
           <span>-></span>
        </div>
      </div>
    {/each}
  </div>
</section>
