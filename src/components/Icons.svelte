<script>
  /** @type {{strokeColor?: string, type: any, width?: string, height?: string}} */
  let {
    strokeColor = '#000',
    type,
    width = '24px;',
    height = '24px;'
  } = $props();
</script>

<div>
  {#if type === 'star'}
    <svg
      width="20"
      height="20"
      viewBox="0 0 20 20"
      fill="currentColor"
      xmlns="http://www.w3.org/2000/svg"
      ><path
        d="M12.43 8L10 0L7.57 8H0L6.18 12.41L3.83 20L10 15.31L16.18 20L13.83 12.41L20 8H12.43Z"
      /></svg
    >
  {:else if type === 'cart'}
    <svg width="20" height="22" viewBox="0 0 20 22" fill="none" stroke={strokeColor}
      ><path
        d="M4 1L1 5V19C1 19.5304 1.21071 20.0391 1.58579 20.4142C1.96086 20.7893 2.46957 21 3 21H17C17.5304 21 18.0391 20.7893 18.4142 20.4142C18.7893 20.0391 19 19.5304 19 19V5L16 1H4Z"
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      /><path d="M1 5H19" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /><path
        d="M14 9C14 10.0609 13.5786 11.0783 12.8284 11.8284C12.0783 12.5786 11.0609 13 10 13C8.93913 13 7.92172 12.5786 7.17157 11.8284C6.42143 11.0783 6 10.0609 6 9"
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      /></svg
    >
  {:else if type === 'close'}
    <svg
      viewBox="0 0 24 24"
      width="24"
      height="24"
      stroke={strokeColor}
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
      fill="none"
      shape-rendering="geometricPrecision"
      class="hover:text-accent-3 h-6 w-6"><path d="M18 6L6 18" /><path d="M6 6l12 12" /></svg
    >
  {:else if type === 'minus'}
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none"
      ><path
        d="M5 12H19"
        stroke={strokeColor}
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      /></svg
    >
  {:else if type === 'plus'}
    <svg width="18" height="18" viewBox="0 0 24 24" fill="none"
      ><path
        d="M12 5V19"
        stroke={strokeColor}
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      /><path
        d="M5 12H19"
        stroke={strokeColor}
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      /></svg
    >
  {:else if type === 'menu'}
    <svg
      xmlns="http://www.w3.org/2000/svg"
      class="h-6 w-6"
      fill="none"
      viewBox="0 0 24 24"
      stroke="#fff"
      ><path
        stroke-linecap="round"
        stroke-linejoin="round"
        stroke-width="2"
        d="M4 6h16M4 12h16m-7 6h7"
      /></svg
    >
  {:else if type === 'search'}
    <svg style={`width:${width};height:${height}`} viewBox="0 0 24 24">
      <path
        fill={strokeColor}
        d="M9.5,3A6.5,6.5 0 0,1 16,9.5C16,11.11 15.41,12.59 14.44,13.73L14.71,14H15.5L20.5,19L19,20.5L14,15.5V14.71L13.73,14.44C12.59,15.41 11.11,16 9.5,16A6.5,6.5 0 0,1 3,9.5A6.5,6.5 0 0,1 9.5,3M9.5,5C7,5 5,7 5,9.5C5,12 7,14 9.5,14C12,14 14,12 14,9.5C14,7 12,5 9.5,5Z"
      />
    </svg>
  {:else if type === 'arrowLeft'}
    <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke={strokeColor}
      ><path d="M19 12H5" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /><path
        d="M12 19L5 12L12 5"
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      /></svg
    >
  {:else if type === 'arrowRight'}
    <svg
      width="24"
      height="24"
      viewBox="0 0 24 24"
      fill="none"
      stroke={strokeColor}
      xmlns="http://www.w3.org/2000/svg"
      ><path d="M5 12H19" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /><path
        d="M12 5L19 12L12 19"
        stroke-width="1.5"
        stroke-linecap="round"
        stroke-linejoin="round"
      /></svg
    >
  {:else if type === 'caretRight'}
    <svg
      viewBox="0 0 24 24"
      width="24"
      height="24"
      stroke={strokeColor}
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
      fill="none"
      shape-rendering="geometricPrecision"
      class="Collapse_icon__JsuEg"><path d="M9 18l6-6-6-6" /></svg
    >
  {:else if type === 'phone'}
    <svg
      style={`width:${width};height:${height}`}
      viewBox="0 0 24 24"
      fill="none"
      stroke={strokeColor}
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
      ><path
        d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72c.127.96.361 1.903.7 2.81a2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45c.907.339 1.85.573 2.81.7A2 2 0 0 1 22 16.92z"
      /></svg
    >
  {:else if type === 'mail'}
    <svg
      style={`width:${width};height:${height}`}
      viewBox="0 0 24 24"
      fill="none"
      stroke={strokeColor}
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
      ><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z" /><path
        d="M22 6l-10 7L2 6"
      /></svg
    >
  {:else if type === 'copy'}
    <svg
      style={`width:${width};height:${height}`}
      viewBox="0 0 24 24"
      fill="none"
      stroke={strokeColor}
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
      ><rect x="9" y="9" width="13" height="13" rx="2" ry="2" /><path
        d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"
      /></svg
    >
  {:else if type === 'check'}
    <svg
      style={`width:${width};height:${height}`}
      viewBox="0 0 24 24"
      fill="none"
      stroke={strokeColor}
      stroke-width="1.5"
      stroke-linecap="round"
      stroke-linejoin="round"
      ><path d="M20 6L9 17L4 12" /></svg
    >
  {/if}
</div>
