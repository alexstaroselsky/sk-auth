<script context="module">
  import { dev } from "$app/env";
  import { session } from "$app/stores";
  import clsx from "clsx";

  export const hydrate = dev;
</script>

<svelte:head>
  <title>Profile | SvelteKitAuth</title>
</svelte:head>

<h1 class={clsx("mb-4")}>Your Profile</h1>

<div class={clsx("flex", "flex-col")}>
  <p class={clsx("text-lg", "mb-2")}>Connections</p>

  <div
    class={clsx(
      "grid",
      "grid-cols-2",
      "sm:grid-cols-3",
      "md:grid-cols-4",
      "lg:grid-cols-6",
      "gap-4",
      "mb-6",
    )}
  >
    <div class={clsx("flex", "items-center", "space-x-4")}>
      <svg viewBox="0 0 128 128" class={clsx("h-4", "w-4", "md:h-6", "md:w-6")}>
        <g id="original">
          <path
            fill="#fff"
            d="M44.59,4.21a63.28,63.28,0,0,0,4.33,120.9,67.6,67.6,0,0,0,32.36.35A57.13,57.13,0,0,0,107.18,112a57.44,57.44,0,0,0,16-26.26,74.33,74.33,0,0,0,1.61-33.58H65.27c0,8.23,0,16.46,0,24.69H99.74A29.72,29.72,0,0,1,87.08,96.37a36.16,36.16,0,0,1-13.93,5.5,41.29,41.29,0,0,1-15.1,0A37.16,37.16,0,0,1,44,95.74a39.3,39.3,0,0,1-14.5-19.42,38.31,38.31,0,0,1,0-24.63,39.25,39.25,0,0,1,9.18-14.91A37.17,37.17,0,0,1,76.13,27a34.28,34.28,0,0,1,13.64,8q5.83-5.8,11.64-11.63c2-2.09,4.18-4.08,6.15-6.22A61.22,61.22,0,0,0,87.2,4.59,64,64,0,0,0,44.59,4.21Z"
          />
          <path
            fill="#e33629"
            d="M44.59,4.21a64,64,0,0,1,42.61.37A61.22,61.22,0,0,1,107.55,17.2c-2,2.14-4.11,4.14-6.15,6.22Q95.58,29.23,89.77,35a34.28,34.28,0,0,0-13.64-8,37.17,37.17,0,0,0-37.46,9.74,39.25,39.25,0,0,0-9.18,14.91L8.76,35.6A63.53,63.53,0,0,1,44.59,4.21Z"
          />
          <path
            fill="#f8bd00"
            d="M3.26,51.5a62.93,62.93,0,0,1,5.5-15.9L29.49,51.69a38.31,38.31,0,0,0,0,24.63q-10.36,8-20.73,16.08A63.33,63.33,0,0,1,3.26,51.5Z"
          />
          <path
            fill="#587dbd"
            d="M65.27,52.15h59.52a74.33,74.33,0,0,1-1.61,33.58,57.44,57.44,0,0,1-16,26.26c-6.69-5.22-13.41-10.4-20.1-15.62A29.72,29.72,0,0,0,99.74,76.83H65.27C65.26,68.61,65.27,60.38,65.27,52.15Z"
          />
          <path
            fill="#319f43"
            d="M8.75,92.4q10.37-8,20.73-16.08A39.3,39.3,0,0,0,44,95.74a37.16,37.16,0,0,0,14.08,6.08,41.29,41.29,0,0,0,15.1,0,36.16,36.16,0,0,0,13.93-5.5c6.69,5.22,13.41,10.4,20.1,15.62a57.13,57.13,0,0,1-25.9,13.47,67.6,67.6,0,0,1-32.36-.35,63,63,0,0,1-23-11.59A63.73,63.73,0,0,1,8.75,92.4Z"
          />
        </g>
      </svg>
      <div class={clsx("flex", "flex-col", "items-start", "space-y-1")}>
        {#if $session.user.connections.google}
          <p class={clsx("font-bold")}>Signed in as:</p>
          {$session.user.connections.google.name}
        {:else}
          <p class={clsx("font-bold")}>Not signed in</p>
          <a
            href="/api/auth/signin/google"
            class={clsx(
              "text-xs",
              "md:text-sm",
              "py-1",
              "px-2",
              "border-gray-400",
              "rounded",
              "hover:no-underline",
              "border",
              "hover:bg-gray-100",
              "transition-colors",
              "items-center",
            )}
          >
            Connect
          </a>
        {/if}
      </div>
    </div>

    <div class={clsx("flex", "items-center", "space-x-4")}>
      <svg viewBox="0 0 128 128" class={clsx("h-4", "w-4", "md:h-6", "md:w-6")}>
        <g id="original">
          <rect
            id="Blue"
            fill="#3d5a98"
            x="4.83"
            y="4.83"
            width="118.35"
            height="118.35"
            rx="6.53"
            ry="6.53"
          />
          <path
            id="f"
            fill="#fff"
            d="M86.48,123.17V77.34h15.38l2.3-17.86H86.48V48.08c0-5.17,1.44-8.7,8.85-8.7h9.46v-16A126.56,126.56,0,0,0,91,22.7C77.38,22.7,68,31,68,46.31V59.48H52.62V77.34H68v45.83Z"
          />
        </g>
      </svg>
      <div class={clsx("flex", "flex-col", "items-start", "space-y-1")}>
        {#if $session.user.connections.facebook}
          <p class={clsx("font-bold")}>Signed in as:</p>
          {$session.user.connections.facebook.name}
        {:else}
          <p class={clsx("font-bold")}>Not signed in</p>
          <a
            href="/api/auth/signin/facebook"
            class={clsx(
              "text-xs",
              "md:text-sm",
              "py-1",
              "px-2",
              "border-gray-400",
              "rounded",
              "hover:no-underline",
              "border",
              "hover:bg-gray-100",
              "transition-colors",
              "items-center",
            )}
          >
            Connect
          </a>
        {/if}
      </div>
    </div>
    <div class={clsx("flex", "items-center", "space-x-4")}>
      <svg viewBox="0 0 24 24" class={clsx("h-4", "w-4", "md:h-6", "md:w-6")}>
        <path
          fill="#FF4300"
          d="M14.5 15.41C14.58 15.5 14.58 15.69 14.5 15.8C13.77 16.5 12.41 16.56 12 16.56C11.61 16.56 10.25 16.5 9.54 15.8C9.44 15.69 9.44 15.5 9.54 15.41C9.65 15.31 9.82 15.31 9.92 15.41C10.38 15.87 11.33 16 12 16C12.69 16 13.66 15.87 14.1 15.41C14.21 15.31 14.38 15.31 14.5 15.41M10.75 13.04C10.75 12.47 10.28 12 9.71 12C9.14 12 8.67 12.47 8.67 13.04C8.67 13.61 9.14 14.09 9.71 14.08C10.28 14.08 10.75 13.61 10.75 13.04M14.29 12C13.72 12 13.25 12.5 13.25 13.05S13.72 14.09 14.29 14.09C14.86 14.09 15.33 13.61 15.33 13.05C15.33 12.5 14.86 12 14.29 12M22 12C22 17.5 17.5 22 12 22S2 17.5 2 12C2 6.5 6.5 2 12 2S22 6.5 22 12M18.67 12C18.67 11.19 18 10.54 17.22 10.54C16.82 10.54 16.46 10.7 16.2 10.95C15.2 10.23 13.83 9.77 12.3 9.71L12.97 6.58L15.14 7.05C15.16 7.6 15.62 8.04 16.18 8.04C16.75 8.04 17.22 7.57 17.22 7C17.22 6.43 16.75 5.96 16.18 5.96C15.77 5.96 15.41 6.2 15.25 6.55L12.82 6.03C12.75 6 12.68 6.03 12.63 6.07C12.57 6.11 12.54 6.17 12.53 6.24L11.79 9.72C10.24 9.77 8.84 10.23 7.82 10.96C7.56 10.71 7.2 10.56 6.81 10.56C6 10.56 5.35 11.21 5.35 12C5.35 12.61 5.71 13.11 6.21 13.34C6.19 13.5 6.18 13.62 6.18 13.78C6.18 16 8.79 17.85 12 17.85C15.23 17.85 17.85 16.03 17.85 13.78C17.85 13.64 17.84 13.5 17.81 13.34C18.31 13.11 18.67 12.6 18.67 12Z"
        />
      </svg>
      <div class={clsx("flex", "flex-col", "items-start", "space-y-1")}>
        {#if $session.user.connections.reddit}
          <p class={clsx("font-bold")}>Signed in as:</p>
          {$session.user.connections.reddit.name}
        {:else}
          <p class={clsx("font-bold")}>Not signed in</p>
          <a
            href="/api/auth/signin/reddit"
            class={clsx(
              "text-xs",
              "md:text-sm",
              "py-1",
              "px-2",
              "border-gray-400",
              "rounded",
              "hover:no-underline",
              "border",
              "hover:bg-gray-100",
              "transition-colors",
              "items-center",
            )}
          >
            Connect
          </a>
        {/if}
      </div>
    </div>
    <div class={clsx("flex", "items-center", "space-x-4")}>
      <svg
        viewBox="0 0 128 128"
        class={clsx("h-4", "w-4", "md:h-6", "md:w-6", "filter", "grayscale", "opacity-60")}
      >
        <g id="surface1">
          <path
            style=" stroke:none;fill-rule:nonzero;fill:rgb(11.372549%,63.137255%,94.901961%);fill-opacity:1;"
            d="M 40.253906 127.636719 C 88.558594 127.636719 114.972656 78.679688 114.972656 36.234375 C 114.972656 34.84375 114.972656 33.457031 114.898438 32.078125 C 120.039062 27.53125 124.476562 21.898438 128 15.445312 C 123.210938 18.046875 118.128906 19.75 112.921875 20.507812 C 118.402344 16.488281 122.503906 10.171875 124.460938 2.734375 C 119.304688 6.476562 113.664062 9.113281 107.78125 10.535156 C 99.644531 -0.0507812 86.710938 -2.644531 76.234375 4.214844 C 65.761719 11.074219 60.351562 25.675781 63.035156 39.832031 C 41.921875 38.539062 22.246094 26.335938 8.914062 6.269531 C 1.933594 20.941406 5.488281 39.722656 17.023438 49.160156 C 12.875 48.988281 8.816406 47.605469 5.191406 45.128906 C 5.191406 45.265625 5.191406 45.402344 5.191406 45.539062 C 5.191406 60.8125 13.976562 73.976562 26.210938 77.03125 C 22.34375 78.320312 18.285156 78.503906 14.347656 77.574219 C 17.785156 90.667969 27.644531 99.644531 38.882812 99.902344 C 29.578125 108.820312 18.089844 113.652344 6.265625 113.621094 C 4.171875 113.621094 2.078125 113.472656 0 113.175781 C 12.007812 122.609375 25.980469 127.617188 40.253906 127.597656 "
          />
        </g>
      </svg>
      <div class={clsx("flex", "flex-col", "items-start", "space-y-1")}>
        {#if $session.user.connections.twitter}
          <p class={clsx("font-bold")}>Signed in as:</p>

          {$session.user.connections.twitter.name}
        {:else}
          <p class={clsx("font-bold")}>Not signed in</p>
          <div
            class={clsx(
              "text-xs",
              "md:text-sm",
              "py-1",
              "px-2",
              "border-gray-400",
              "rounded",
              "hover:no-underline",
              "border",
              "hover:bg-gray-100",
              "transition-colors",
              "items-center",
              "cursor-not-allowed",
              "inline-block",
            )}
          >
            Connect
          </div>
        {/if}
      </div>
    </div>
    <div class={clsx("flex", "items-center", "space-x-4")}>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        version="1.1"
        viewBox="0 0 168 168"
        class={clsx("h-4", "w-4", "md:h-6", "md:w-6")}
      >
        <path
          fill="#1ED760"
          d="m83.996 0.277c-46.249 0-83.743 37.493-83.743 83.742 0 46.251 37.494 83.741 83.743 83.741 46.254 0 83.744-37.49 83.744-83.741 0-46.246-37.49-83.738-83.745-83.738l0.001-0.004zm38.404 120.78c-1.5 2.46-4.72 3.24-7.18 1.73-19.662-12.01-44.414-14.73-73.564-8.07-2.809 0.64-5.609-1.12-6.249-3.93-0.643-2.81 1.11-5.61 3.926-6.25 31.9-7.291 59.263-4.15 81.337 9.34 2.46 1.51 3.24 4.72 1.73 7.18zm10.25-22.805c-1.89 3.075-5.91 4.045-8.98 2.155-22.51-13.839-56.823-17.846-83.448-9.764-3.453 1.043-7.1-0.903-8.148-4.35-1.04-3.453 0.907-7.093 4.354-8.143 30.413-9.228 68.222-4.758 94.072 11.127 3.07 1.89 4.04 5.91 2.15 8.976v-0.001zm0.88-23.744c-26.99-16.031-71.52-17.505-97.289-9.684-4.138 1.255-8.514-1.081-9.768-5.219-1.254-4.14 1.08-8.513 5.221-9.771 29.581-8.98 78.756-7.245 109.83 11.202 3.73 2.209 4.95 7.016 2.74 10.733-2.2 3.722-7.02 4.949-10.73 2.739z"
        />
      </svg>
      <div class={clsx("flex", "flex-col", "items-start", "space-y-1")}>
        {#if $session.user.connections.spotify}
          <p class={clsx("font-bold")}>Signed in as:</p>

          {$session.user.connections.spotify.display_name}
        {:else}
          <p class={clsx("font-bold")}>Not signed in</p>
          <div
            class={clsx(
              "text-xs",
              "md:text-sm",
              "py-1",
              "px-2",
              "border-gray-400",
              "rounded",
              "hover:no-underline",
              "border",
              "hover:bg-gray-100",
              "transition-colors",
              "items-center",
              "cursor-not-allowed",
              "inline-block",
            )}
          >
            Connect
          </div>
        {/if}
      </div>
    </div>
  </div>

  <p class={clsx("text-lg", "mb-2")}>Session</p>
  <pre
    class={clsx(
      "bg-gray-100",
      "whitespace-pre-wrap",
      "p-3",
    )}>
    <code>{JSON.stringify($session, null, 2)}</code>
  </pre>
</div>
