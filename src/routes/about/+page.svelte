<script>
  import Icons from '$components/Icons.svelte';

  const contactMethods = [
    {
      key: 'phone',
      icon: 'phone',
      label: 'Call Us',
      display: '(832) 520-1187',
      value: '832-520-1187',
      href: 'tel:+18325201187',
      actionLabel: 'Call'
    },
    {
      key: 'email',
      icon: 'mail',
      label: 'Email Us',
      display: 'carson.combs@centre.edu',
      value: 'carson.combs@centre.edu',
      href: 'mailto:carson.combs@centre.edu',
      actionLabel: 'Email'
    }
  ];

  let copiedKey = $state('');

  async function copyToClipboard(text, key) {
    try {
      await navigator.clipboard.writeText(text);
      copiedKey = key;
      setTimeout(() => {
        if (copiedKey === key) copiedKey = '';
      }, 2000);
    } catch (err) {
      console.error('Failed to copy to clipboard', err);
    }
  }
</script>

<svelte:head>
  <title>About Us – SvelteKit Commerce</title>
</svelte:head>

<main class="mx-auto max-w-4xl px-4 py-16 sm:px-6 lg:px-8">
  <section>
    <h1 class="text-3xl font-black text-white md:text-4xl">About Us</h1>
    <p class="mt-4 text-lg text-zinc-300">
      Cupcake ipsum dolor sit amet lemon drops pastry cotton candy. Sweet carrot cake macaroon
      bonbon croissant fruitcake jujubes macaroon oat cake.
    </p>
  </section>

  <section class="mt-12 rounded-lg border border-zinc-700 bg-dark p-6 sm:p-8">
    <h2 class="text-2xl font-bold text-white">Contact Us</h2>
    <p class="mt-2 text-zinc-300">Reach out by phone or email — tap to act, or copy the details.</p>

    <div class="mt-6 grid gap-4 sm:grid-cols-2">
      {#each contactMethods as method (method.key)}
        <div class="flex flex-col justify-between rounded-lg border border-zinc-700 p-4">
          <div class="flex items-center gap-3">
            <div class="flex h-10 w-10 flex-none items-center justify-center rounded-full bg-zinc-800">
              <Icons type={method.icon} strokeColor="#fff" width="18px" height="18px" />
            </div>
            <div class="min-w-0">
              <div class="text-sm text-zinc-400">{method.label}</div>
              <div class="truncate font-medium text-white">{method.display}</div>
            </div>
          </div>
          <div class="mt-4 flex gap-2">
            <a
              href={method.href}
              class="flex flex-1 items-center justify-center gap-2 rounded-lg bg-white px-3 py-2 text-sm font-bold text-black hover:opacity-90"
            >
              <Icons type={method.icon} strokeColor="#000" width="16px" height="16px" />
              {method.actionLabel}
            </a>
            <button
              type="button"
              onclick={() => copyToClipboard(method.value, method.key)}
              aria-label={`Copy ${method.label.toLowerCase()}`}
              class="flex items-center justify-center gap-2 rounded-lg border border-zinc-700 px-3 py-2 text-sm font-medium text-white hover:bg-zinc-800 cursor-pointer"
            >
              {#if copiedKey === method.key}
                <Icons type="check" strokeColor="#fff" width="16px" height="16px" />
                Copied
              {:else}
                <Icons type="copy" strokeColor="#fff" width="16px" height="16px" />
                Copy
              {/if}
            </button>
          </div>
        </div>
      {/each}
    </div>
  </section>
</main>
