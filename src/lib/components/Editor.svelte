<script lang="ts">
  import * as monaco from "monaco-editor";
  import latex from "monaco-latex";
  import { onMount } from "svelte";

  let container: HTMLDivElement;

  onMount(() => {
    const value = `\\documentclass{article}
\\usepackage{graphicx}

\\title{Project Name}
\\author{Name}
\\date{Insert Date}

\\begin{document}
\\maketitle
\\section{Introduction}
\\end{document}`;

    monaco.languages.register({ id: "latex" });
    monaco.languages.setMonarchTokensProvider("latex", latex);

    monaco.editor.create(container, {
      value,
      language: "latex", 
      automaticLayout: true,
      theme: "vs-dark",
    });
  });
</script>

<div bind:this={container} class="editor-container"></div>

<style>
  .editor-container {
    width: 100%;
    border: 1px solid pink;
    overflow: hidden;
  }
</style>
