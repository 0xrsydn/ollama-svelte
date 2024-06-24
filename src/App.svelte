<script lang="ts">
  import { onMount } from 'svelte';
  import { marked } from 'marked';
  import ollamaImage from './assets/ollama.png';

  let prompt = '';
  let response = '';
  let loading = false;
  let error = '';

  async function generateResponse() {
    error = ''; // Clear any previous errors
    loading = true; // Set loading state

    const url = 'http://localhost:11434/api/generate';
    const payload = {
      model: 'llama3',
      prompt: prompt,
      stream: false
    };

    try {
      const response2 = await fetch(url, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json'
        },
        body: JSON.stringify(payload)
      });

      if (!response2.ok) {
        throw new Error('Failed to generate response');
      }

      const data = await response2.json();
      response = marked(data.response); // Parse the response with marked
    } catch (err) {
      error = err.message;
    } finally {
      loading = false; // Clear loading state
    }
  }
</script>

<main class="flex flex-col items-center justify-center min-h-screen py-2">
  <img src={ollamaImage} alt="Ollama" class="mb-4 w-35 h-40" />
  <h1 class="text-4xl font-bold text-center text-gray-800">Ollama REST API Test</h1>
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
      <div class="mt-2 text-gray-700">{@html response}</div>
    </div>
  {/if}
</main>