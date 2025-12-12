<script lang="ts">
  import { onMount } from 'svelte';

  const steps = [
    {
      id: "network",
      title: "Access an Elite Network",
      text: "Connect with 2,000+ member companies and 4,000+ business leaders who collectively represent over 40% of Brazil's private GDP. Gain access to CEOs and C-level executives across 39 economic sectors who can transform your business trajectory.",
      tags: ["Exclusive CEO Forums", "C-Level Connections", "Sectorial Networks", "International Partnerships", "Strategic Alliances", "Peer-to-Peer Learning"],
      graphic: "lines"
    },
    {
      id: "expand",
      title: "Expand Globally",
      text: "Leverage LIDE's presence across 19 countries and 5 continents. Participate in international forums in New York, Paris, London, Dubai, Tokyo, and beyond. Build bilateral relationships that open new markets and opportunities for your business.",
      tags: ["Global Forums", "International Events", "Market Expansion", "Cross-Border Partnerships", "Bilateral Relations", "Investment Opportunities"],
      graphic: "curve"
    },
    {
      id: "influence",
      title: "Shape Economic Policy",
      text: "Join sectorial committees led by former ministers, industry authorities, and thought leaders. Participate in discussions that influence economic policy and drive socioeconomic development. Your voice matters in shaping the future of business.",
      tags: ["Policy Influence", "Sectorial Leadership", "Economic Forums", "Government Relations", "Industry Advocacy", "Thought Leadership"],
      graphic: "circle-top"
    },
    {
      id: "grow",
      title: "Accelerate Business Growth",
      text: "Transform connections into concrete business opportunities. Through exclusive events, strategic forums, and trusted peer relationships, LIDE members generate partnerships, close deals, and accelerate growth in ways impossible to achieve alone.",
      tags: ["Business Development", "Partnership Creation", "Deal Flow", "Market Intelligence", "Strategic Positioning", "Growth Acceleration"],
      graphic: "circle-waves"
    }
  ];

  let activeStep = 0;
  let sectionRef: HTMLElement;

  onMount(() => {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            const index = steps.findIndex(step => step.id === entry.target.id);
            if (index !== -1) {
              activeStep = index;
            }
          }
        });
      },
      {
        root: null,
        rootMargin: "-20% 0px -20% 0px", // Trigger when element is in the middle 60% of viewport
        threshold: 0.5
      }
    );

    steps.forEach((step) => {
      const el = document.getElementById(step.id);
      if (el) observer.observe(el);
    });

    return () => observer.disconnect();
  });
</script>

<section class="bg-[#1a1a40] text-white py-24 px-6 md:px-12 relative" bind:this={sectionRef}>
  <div class="max-w-screen-2xl mx-auto flex flex-col md:flex-row gap-12">
    
    <!-- Sticky Navigation -->
    <div class="md:w-1/2 md:h-[calc(100vh-6rem)] md:sticky md:top-24 flex flex-col justify-center">
      <div class="space-y-8">
        {#each steps as step, i}
          <div class="transition-opacity duration-500 {i === activeStep ? 'opacity-100' : 'opacity-30'}">
            <p class="text-xl md:text-2xl font-light mb-1">Members join LIDE to</p>
            <h2 class="text-2xl md:text-3xl font-bold">{step.title}</h2>
          </div>
        {/each}
      </div>
    </div>

    <!-- Scrollable Cards -->
    <div class="md:w-1/2 space-y-24 pt-12 md:pt-0">
      {#each steps as step, i}
        <div class="bg-white text-black rounded-lg p-8 md:p-12 min-h-[600px] flex flex-col justify-between scroll-mt-32" id={step.id}>
          <!-- Graphic Placeholder -->
          <div class="flex-1 flex items-center justify-center mb-8 border border-gray-100 rounded bg-gray-50 min-h-[200px]">
             {#if step.graphic === 'lines'}
                <svg width="200" height="100" viewBox="0 0 200 100" class="opacity-50">
                    <line x1="20" y1="20" x2="20" y2="80" stroke="black" stroke-width="1"/>
                    <line x1="40" y1="20" x2="40" y2="80" stroke="black" stroke-width="1"/>
                    <line x1="60" y1="20" x2="60" y2="80" stroke="black" stroke-width="1"/>
                    <line x1="80" y1="20" x2="80" y2="80" stroke="black" stroke-width="1"/>
                    <line x1="100" y1="20" x2="100" y2="80" stroke="black" stroke-width="1"/>
                </svg>
             {:else if step.graphic === 'curve'}
                <svg width="200" height="100" viewBox="0 0 200 100" class="opacity-50">
                    <path d="M20 80 Q 100 0 180 80" fill="none" stroke="black" stroke-width="1"/>
                </svg>
             {:else if step.graphic === 'circle-top'}
                <svg width="200" height="100" viewBox="0 0 200 100" class="opacity-50">
                    <circle cx="100" cy="100" r="60" fill="none" stroke="black" stroke-width="1"/>
                    <circle cx="100" cy="100" r="40" fill="none" stroke="black" stroke-width="1"/>
                </svg>
             {:else}
                <svg width="200" height="100" viewBox="0 0 200 100" class="opacity-50">
                    <ellipse cx="100" cy="50" rx="80" ry="20" fill="none" stroke="black" stroke-width="1"/>
                    <ellipse cx="100" cy="50" rx="60" ry="15" fill="none" stroke="black" stroke-width="1"/>
                    <ellipse cx="100" cy="50" rx="40" ry="10" fill="none" stroke="black" stroke-width="1"/>
                </svg>
             {/if}
          </div>

          <div>
             <p class="text-lg leading-relaxed mb-8">{step.text}</p>

             <div class="grid grid-cols-2 gap-4 text-xs font-medium text-gray-600">
               {#each step.tags as tag}
                 <div class="flex items-center gap-2">
                   <span class="w-1.5 h-1.5 bg-black rounded-full shrink-0"></span>
                   {tag}
                 </div>
               {/each}
             </div>
          </div>
        </div>
      {/each}
    </div>
  </div>
</section>
