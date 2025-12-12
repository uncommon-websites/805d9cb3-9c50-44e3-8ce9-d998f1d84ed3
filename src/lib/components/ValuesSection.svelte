<script lang="ts">
  const photos = [
    {
      title: "Exclusive Networking",
      desc: "Connect with CEOs and C-level executives at intimate evening events designed to foster meaningful relationships.",
      img: "/generated/image-business-leaders-networking-at-an-exclus-1765529554962-7.webp"
    },
    {
      title: "Strategic Dialogue",
      desc: "Engage in high-level discussions with peers who understand your challenges and can offer valuable insights.",
      img: "/generated/image-ceos-and-executives-in-discussion-at-a-m-1765529557688-8.webp"
    },
    {
      title: "Global Forums",
      desc: "Participate in international conferences that connect you with business leaders across continents and cultures.",
      img: "/generated/image-international-business-forum-with-flags--1765529560209-9.webp"
    }
  ];
</script>

<section class="py-24 px-6 md:px-12 bg-white">
  <div class="max-w-xl mb-16">
    <h3 class="text-lg font-bold mb-2">We create spaces for authentic connection.</h3>
    <p class="text-gray-500 text-sm leading-relaxed">
      In a world where trust is currency, LIDE provides the platform for CEOs and business leaders to build genuine relationships. Our exclusive events and forums are designed to facilitate meaningful connections that translate into lasting partnerships and business opportunities.
    </p>
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
    {#each photos as photo}
      <div>
        <div class="aspect-[3/4] rounded-lg overflow-hidden mb-4 bg-gray-100">
          <img src={photo.img} alt={photo.title} class="w-full h-full object-cover" />
        </div>
        <h4 class="text-xs font-bold mb-1">{photo.title}</h4>
        <p class="text-[10px] text-gray-500 leading-relaxed">{photo.desc}</p>
      </div>
    {/each}
  </div>
</section>
