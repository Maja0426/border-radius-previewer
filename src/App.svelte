<script>
  let btr = 0;
  let btl = 0;
  let bbr = 0;
  let bbl = 0;
  $: copyText = `\nborder-top-right-radius: ${btr}%;\nborder-top-left-radius: ${btl}%;\nborder-bottom-right-radius: ${bbr}%;\nborder-bottom-left-radius: ${bbl}%;\n`;

  function copied() {
    let copied = document.getElementById("copy-code");
    copied.select();
    copied.setSelectionRange(0, 99999);
    document.execCommand("copy");
    /* alert("Copied the text: " + copied.value); */
  }
</script>

<style>
  main {
    min-height: 93vh;
    position: relative;
    text-align: center;
    background-color: #ffffff;
    color: #333;
    margin: 0;
    box-sizing: border-box;
  }

  h1 {
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 3em;
    font-weight: 100;
    margin-bottom: 0;
  }

  .main {
    display: flex;
    flex-direction: column;
    width: 400px;
    margin: 0 auto 2em;
    justify-content: center;
    align-items: center;
  }

  .original {
    position: absolute;
    left: -1px;
    top: -1px;
    width: 100%;
    height: 100%;
    border: 1px dashed #f12711;
  }

  .object {
    position: relative;
    padding: 0;
    margin: 1rem;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 400px;
    height: 400px;
    background: linear-gradient(to left, #f15120, #f12711);
    border: 1px solid #f12711;
  }

  .slide {
    margin-bottom: 1em;
    width: 100%;
  }

  .slider {
    -webkit-appearance: none;
    width: 100%;
    height: 5px;
    border-radius: 5px;
    background: #d3d3d3;
    outline: none;
    opacity: 1;
    -webkit-transition: 0.2s;
    transition: opacity 0.2s;
  }

  .slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 25px;
    height: 25px;
    border-radius: 50%;
    background: #ff3e00;
    cursor: pointer;
  }

  .slider::-moz-range-thumb {
    width: 25px;
    height: 25px;
    border-radius: 50%;
    background: #ff3e00;
    cursor: pointer;
  }

  textarea {
    width: 100%;
    background: #333;
    color: #d3d3d3;
    text-align: center;
  }

  button {
    display: block;
    margin-top: 5px;
    width: 100%;
  }

  footer {
    min-height: 7vh;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0 4em;
    margin: 0 auto;
    background: #333;
    color: #d3d3d3;
  }

  img {
    width: 4vh;
    margin: 0 1em;
  }

  @media (max-width: 640px) {
    h1 {
      font-size: 2em;
    }

    .main {
      width: 300px;
    }

    .object {
      width: 300px;
      height: 300px;
    }
  }

  @media (max-width: 420px) {
    h1 {
      font-size: 2em;
    }

    .main {
      width: 300px;
    }

    .object {
      width: 250px;
      height: 250px;
    }
  }

  @media (max-width: 320px) {
    h1 {
      font-size: 1.8em;
    }

    .main {
      width: 200px;
    }

    .object {
      width: 200px;
      height: 200px;
    }
  }
</style>

<main>
  <div>
    <h1>Border Radius Previewer</h1>
    <p>
      Border Radius Previewer,
      <a
        href="https://github.com/florinpop17/app-ideas"
        title="https://github.com/florinpop17/app-ideas"
        target="_blank"
        rel="noreferrer">
        florinpop17 app-ideas
      </a>
      collection, this is
      <a
        href="https://github.com/Maja0426/border-radius-previewer"
        target="_blank"
        rel="noreferrer"
        title="Github repo">
        my version
      </a>
      .
    </p>
  </div>
  <section class="main">
    <div
      class="object"
      style="border-top-right-radius: {btr}%; border-top-left-radius: {btl}%;
      border-bottom-right-radius: {bbr}%; border-bottom-left-radius: {bbl}%">
      <div class="original" />
    </div>
    <div class="slide">
      <input
        class="slider"
        type="range"
        min="0"
        max="100"
        id="btr"
        step="1"
        bind:value={btr}
        title="border-top-right-radius" />
    </div>

    <div class="slide">
      <input
        class="slider"
        type="range"
        min="0"
        max="100"
        id="btl"
        step="1"
        bind:value={btl}
        title="border-top-left-radius" />
    </div>

    <div class="slide">
      <input
        class="slider"
        type="range"
        min="0"
        max="100"
        id="bbr"
        step="1"
        bind:value={bbr}
        title="border-bottom-right-radius" />
    </div>

    <div class="slide">
      <input
        class="slider"
        type="range"
        min="0"
        max="100"
        id="bbr"
        step="1"
        bind:value={bbl}
        title="border-bottom-left-radius" />
    </div>
    <textarea type="text" id="copy-code" rows="6">{copyText}</textarea>
    <button on:click|preventDefault={copied} id="copy">Copy Code</button>
  </section>
</main>

<footer>
  <p>&copy;Tamas Majoros</p>
  <div class="links">
    <a
      href="https://www.linkedin.com/in/majoros-tamas/"
      target="_blank"
      rel="noreferrer">
      <img src="./linkedin.svg" alt="facebook logo" />
    </a>
    <a href="https://twitter.com/tmajoros" target="_blank" rel="noreferrer">
      <img src="../twitter.svg" alt="twitter logo" />
    </a>
    <a
      href="https://www.instagram.com/smartbeeweboldalak/"
      target="_blank"
      rel="noreferrer">
      <img src="../instagram.svg" alt="instagram logo" />
    </a>
  </div>
</footer>
