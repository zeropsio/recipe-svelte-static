<script lang="ts">
import { writable } from 'svelte/store';

export let code: string;
export let file: string;
export let fileLink: string;

const CopyIcon = `<svg
    xmlns="http://www.w3.org/2000/svg"
    width="20"
    height="20"
    viewBox="0 0 24 24"
    fill="none"
    stroke="currentColor"
    strokeWidth="2"
    strokeLinecap="round"
    strokeLinejoin="round"
  >
    <rect x="9" y="9" width="13" height="13" rx="2" ry="2"></rect>
    <path d="M5 15H4a2 2 0 0 1-2-2V4a2 2 0 0 1 2-2h9a2 2 0 0 1 2 2v1"></path>
  </svg>`;

const CheckIcon = `<svg xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" strokeWidth="2" strokeLinecap="round" strokeLinejoin="round">
    <polyline points="20 6 9 17 4 12"></polyline>
</svg>`;

let icon = writable(CopyIcon);

const copy = async () => {
    await navigator.clipboard.writeText(code);
    icon.set(CheckIcon);
    setTimeout(() => icon.set(CopyIcon), 2000);
};

    function innerHtml(node, html) {
        const unsubscribe = html.subscribe(value => {
            node.innerHTML = value;
        });

        return {
            destroy() {
                unsubscribe();
            }
        };
    }
</script>

<div class="my-8 bg-[#383838] font-medium h-full rounded-md">
	<span class="flex justify-center py-1 text-sm">
    <a href={fileLink} target="_blank" class="filelink">{file}</a>

	</span>
    <pre class="bg-[#242424] rounded-b-md h-full p-8 relative flex">
            <button
                on:click={copy}
                class="absolute top-4 right-4 p-3 rounded-md bg-[#383838] text-[#ccc]"
                use:innerHtml={icon}
            ></button>
        <code class="text-[#ccc] font-medium text-sm flex items-start  overflow-x-auto">{code}</code>
    </pre>
</div>
