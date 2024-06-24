<!-- <script lang="ts">
    import { marked } from 'marked';
  
    export let prompt: string = '';
    export let loading: boolean = false;
    export let error: string = '';
    export let response: string = '';
  
    async function generateResponse() {
      console.log('generateResponse called');
      // This function should be defined in the parent component
    }
  </script>
  
  <div class="flex flex-col items-center justify-center min-h-screen py-2">
    <h1 class="text-4xl font-bold text-center text-gray-800">Ollama API Tester</h1>
    <input
      type="text"
      bind:value={prompt}
      placeholder="Enter your prompt"
      class="mt-4 p-2 border border-gray-300 rounded-md w-64"
    />
    <button
      on:click={generateResponse}
      class="mt-4 px-4 py-2 bg-blue-500 text-white rounded-md hover:bg-blue-600"
      disabled={loading}
    >
      {#if loading}
        Generating...
      {:else}
        Generate Response
      {/if}
    </button>
    {#if error}
      <div class="mt-4 text-red-500">
        Error: {error}
      </div>
    {/if}
    {#if response}
      <div class="mt-4">
        <h2 class="text-2xl font-semibold text-gray-800">Response:</h2>
        <div class="mt-2 text-gray-700">{@html marked(response)}</div>
      </div>
    {/if}
  </div> -->