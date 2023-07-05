<script>
  let mode = localStorage.getItem("_mode") || "Lite";
/**
  @param {string} mode - Lite or Dark
**/

  import "../engine/docs.css"

  import { onMount } from 'svelte';

  let parse = [["h1", "h1-style"]];
  let parsedContent = '';
  let documentTree = [];
  /*
  [
    ["Svelte Docs", 1],
    ["連絡先", 2]
  ]
  */

  onMount(() => {
    const docsElement = document.querySelector('docs');
    const childElements = Array.from(docsElement.children);

    const parsedChildren = childElements.map(child => {
      const originalTagName = child.tagName.toLowerCase();
      let modifiedTagName = originalTagName;

      if (modifiedTagName == "h1") {
        documentTree.push([child.innerHTML, 1])
      }else if (modifiedTagName == "h2") {
        documentTree.push([child.innerHTML, 2])
      }else if (modifiedTagName == "h3") {
        documentTree.push([child.innerHTML, 3])
      }else if (modifiedTagName == "h4") {
        documentTree.push([child.innerHTML, 4])
      }else if (modifiedTagName == "h5") {
        documentTree.push([child.innerHTML, 5])
      }else if (modifiedTagName == "h6") {
        documentTree.push([child.innerHTML, 6])
      }

      parse.forEach(([tag, parsedTag]) => {
        if (originalTagName === tag) {
          modifiedTagName = parsedTag;
        }
      }); // parseTag

      const modifiedChild = document.createElement(modifiedTagName);
      Array.from(child.attributes).forEach(attr => {
        modifiedChild.setAttribute(attr.name, attr.value);
      });
      modifiedChild.innerHTML = child.innerHTML;

      return modifiedChild.outerHTML;
    });
    parsedContent = parsedChildren.join('');
  });
</script>

<docs class="hidden">
  <h1>Svelte Docs</h1>
  <p>document書いてくれる方募集中。</p>
  <p>大体見れば分かります。</p>
  <h2>連絡先</h2>
  <p>@macl2189 / @EdamAme-x</p>
  <h3>test</h3>
  
  <div id="tree">

  </div>
</docs>

  {@html parsedContent}
<style>
  
</style>