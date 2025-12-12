<script lang="ts">
  const stats = [
    {
      label: "2,000+ Companies",
      desc: "Over 2,000 member companies and 4,000+ individual business leaders participate in LIDE's exclusive network. Our members collectively represent over 40% of Brazil's private GDP, making LIDE the most influential business organization in Latin America.",
      img: "/generated/image-diverse-group-of-ceos-and-business-leade-1765529546897-4.webp"
    },
    {
      label: "19 Countries",
      desc: "LIDE operates across 19 countries on 5 continents with offices and representation units spanning from Brazil to the United States, Europe, Middle East, and Asia. Our global presence includes 28 national units in Brazil and 21 international units worldwide.",
      img: "/generated/image-international-business-forum-with-flags--1765529560209-9.webp"
    },
    {
      label: "39 Sectors",
      desc: "From agribusiness to technology, energy to healthcare, LIDE covers 39 economic sectors. Each sector is led by prominent business figures and authorities, including former ministers and industry leaders who drive meaningful discussions and policy influence.",
      img: "/generated/image-business-leaders-shaking-hands-at-a-sect-1765529544521-3.webp"
    },
    {
      label: "40% of GDP",
      desc: "LIDE's Brazilian members collectively represent over 40% of Brazil's private GDP. This unprecedented economic influence allows our network to shape policy, drive innovation, and contribute significantly to the socioeconomic development of nations.",
      img: "/generated/image-elegant-business-forum-with-ceos-and-exe-1765529536398-0.webp"
    }
  ];
</script>

<section class="py-24 px-6 md:px-12 bg-white border-t border-gray-100">
  <div class="mb-16">
    <p class="text-gray-500 max-w-xl">
      LIDE's impact extends far beyond networking. Here's a snapshot of our global reach, economic influence, and the scale of leadership we bring together.
    </p>
  </div>

  <div class="space-y-16">
    {#each stats as stat}
      <div class="flex flex-col md:flex-row md:items-start justify-between gap-8 border-b border-gray-100 pb-16 last:border-0">
        <h3 class="text-2xl md:text-4xl font-medium w-full md:w-1/3">{stat.label}</h3>
        <div class="w-full md:w-1/3">
           <p class="text-xs leading-relaxed text-gray-500">{stat.desc}</p>
        </div>
        <div class="w-full md:w-1/6 flex justify-end">
           <img src={stat.img} alt={stat.label} class="w-20 h-20 object-cover rounded bg-gray-100" />
        </div>
      </div>
    {/each}
  </div>
</section>
