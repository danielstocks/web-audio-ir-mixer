<script lang="ts">
  // ENUM: allowed values: mono, dual mono, stereo.
  export let inputRouting = "mono";

  // Pan left to right.
  // The pan property takes a unitless value between -1 (full left pan) and 1 (full right pan).
  export let balance = 0;

  // Output level 0-1
  export let outputLevel = 0;

  export const deckA = {
    // normal or invert
    phase: "normal",
    active: false,
    // The pan property takes a unitless value between -1 (full left pan) and 1 (full right pan).
    pan: 0,
    // Output level 0-1
    level: 0,
  };
</script>

<style>
  main {
    padding: 1em;
    max-width: 1024px;
    margin: 0 auto;
  }

  .input-range {
    margin: 0;
    width: 75px;
  }

  .col {
    display: flex;
  }

  .col-center {
    align-items: center;
  }

  .row {
    display: flex;
    flex-direction: column;
  }

  .spacer-0 {
    flex-basis: 6px;
  }

  .spacer-1 {
    flex-basis: 12px;
  }

  .spacer-2 {
    flex-basis: 24px;
  }

  .grow {
    flex: 1;
  }

  .ir-sample-list {
    background: #000;
    padding: 6px;
    display: flex;
    flex-direction: column;
  }
  .ir-sample-list-item {
    font-size: 12px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .remove-btn {
    font-size: 10px;
    -webkit-appearance: none;
    padding: 2px 4px;
    background: transparent;
    color: #fff;
    border: 1px solid #fff;
  }

  h2 {
    border-bottom: 1px solid #fff;
    padding-bottom: 6px;
    margin: 0;
  }

  input[type="file"] {
    width: 100%;
  }
</style>

<main>

  <div class="row">

    <h2>Master</h2>
    <div class="spacer-2" />

    <div class="col">
      <fieldset class="row grow">
        <div class="spacer-1" />
        <legend>Input Routing</legend>
        <label class="col col-center">
          <input name="inputRouting" checked value="mono" type="radio" />
          <div class="spacer-0" />
          Mono
        </label>
        <label>
          <input name="inputRouting" value="stereo" type="radio" />
          Stereo
        </label>
        <label>
          <input name="inputRouting" value="dual-mono" type="radio" />
          Dual Mono
        </label>
      </fieldset>

      <div class="spacer-2" />

      <fieldset class="row grow">
        <legend>Balance</legend>
        <div class="spacer-1" />
        <label class="col col-center">
          <div>A</div>
          <div class="spacer-1" />
          <input class="input-range" type="range" />
          <div class="spacer-1" />
          <div>B</div>
        </label>
      </fieldset>

      <div class="spacer-2" />

      <fieldset class="row grow">
        <legend>Output</legend>
        <div class="spacer-1" />
        <label class="col col-center">
          <div>0</div>
          <div class="spacer-1" />
          <input class="input-range" type="range" />
          <div class="spacer-1" />
          <div>10</div>
        </label>
      </fieldset>
    </div>

    <div class="spacer-2" />

    <div class="col">

      <div class="row grow">
        <h2>A</h2>
        <div class="spacer-2" />
        <fieldset class="row">
          <div class="spacer-1" />
          <legend>Operation</legend>
          <label>
            <input name="deck-a-operation" checked value="on" type="radio" />
            On
          </label>
          <label>
            <input name="deck-a-operation" value="off" type="radio" />
            Off
          </label>
        </fieldset>
        <div class="spacer-2" />
        <fieldset class="row">
          <div class="spacer-1" />
          <legend>Phase</legend>
          <label>
            <input name="deck-a-phase" checked value="normal" type="radio" />
            Normal
          </label>
          <label>
            <input name="deck-a-phase" value="invert" type="radio" />
            Invert
          </label>
        </fieldset>
        <div class="spacer-2" />
        <fieldset class="row">
          <div class="spacer-1" />
          <legend>Load IR</legend>
          <div class="ir-sample-list">
            <div class="ir-sample-list-item">
              <label>
                <input
                  name="deck-a-selected-ir"
                  checked
                  value="normal"
                  type="radio" />
                deluxe-reverb-close.wav
              </label>
              <button class="remove-btn">×</button>
            </div>
            <div class="spacer-0" />
            <div class="ir-sample-list-item">
              <label>
                <input
                  name="deck-a-selected-ir"
                  checked
                  value="normal"
                  type="radio" />
                super-reverb-far-away.wav
              </label>
              <button class="remove-btn">×</button>
            </div>
          </div>
          <div class="spacer-0" />
          <div class="col">

            <input name="deck-a-operation" checked value="on" type="file" />

            <div class="spacer-0" />
            <button>▲</button>
            <div class="spacer-0" />
            <button>▼</button>
          </div>
        </fieldset>

        <div class="spacer-2" />

        <div class="col">
          <fieldset class="row grow">
            <leged>Pan</leged>
            <div class="spacer-1" />
            <label class="col col-center">
              <div>L</div>
              <div class="spacer-1" />
              <input class="input-range" type="range" />
              <div class="spacer-1" />
              <div>R</div>
            </label>
          </fieldset>

          <div class="spacer-1" />

          <fieldset class="row grow">
            <leged>Level</leged>
            <div class="spacer-1" />
            <label class="col col-center">
              <div>0</div>
              <div class="spacer-1" />
              <input class="input-range" type="range" />
              <div class="spacer-1" />
              <div>10</div>
            </label>
          </fieldset>
        </div>
      </div>

      <div class="spacer-2" />

      <div class="row grow">
        <h2>B</h2>
        <div class="spacer-2" />
        <fieldset class="row">
          <div class="spacer-1" />
          <legend>Operation</legend>
          <label>
            <input name="deck-a-operation" checked value="on" type="radio" />
            On
          </label>
          <label>
            <input name="deck-a-operation" value="off" type="radio" />
            Off
          </label>
        </fieldset>
        <div class="spacer-2" />
        <fieldset class="row">
          <div class="spacer-1" />
          <legend>Phase</legend>
          <label>
            <input name="deck-a-phase" checked value="normal" type="radio" />
            Normal
          </label>
          <label>
            <input name="deck-a-phase" value="invert" type="radio" />
            Invert
          </label>
        </fieldset>
        <div class="spacer-2" />
        <fieldset class="row">
          <div class="spacer-1" />
          <legend>Load IR</legend>
          <div class="ir-sample-list">
            <div class="ir-sample-list-item">
              <label>
                <input
                  name="deck-a-selected-ir"
                  checked
                  value="normal"
                  type="radio" />
                deluxe-reverb-close.wav
              </label>
              <button class="remove-btn">×</button>
            </div>
            <div class="spacer-0" />
            <div class="ir-sample-list-item">
              <label>
                <input
                  name="deck-a-selected-ir"
                  checked
                  value="normal"
                  type="radio" />
                super-reverb-far-away.wav
              </label>
              <button class="remove-btn">×</button>
            </div>
          </div>
          <div class="spacer-0" />
          <div class="col">

            <input name="deck-a-operation" checked value="on" type="file" />

            <div class="spacer-0" />
            <button>▲</button>
            <div class="spacer-0" />
            <button>▼</button>
          </div>
        </fieldset>

        <div class="spacer-2" />

        <div class="col">
          <fieldset class="row grow">
            <leged>Pan</leged>
            <div class="spacer-1" />
            <label class="col col-center">
              <div>L</div>
              <div class="spacer-1" />
              <input class="input-range" type="range" />
              <div class="spacer-1" />
              <div>R</div>
            </label>
          </fieldset>

          <div class="spacer-1" />

          <fieldset class="row grow">
            <leged>Level</leged>
            <div class="spacer-1" />
            <label class="col col-center">
              <div>0</div>
              <div class="spacer-1" />
              <input
                class="input-range"
                type="range"
                min="0"
                max="10"
                step="1" />
              <div class="spacer-1" />
              <div>10</div>
            </label>
          </fieldset>
        </div>
      </div>

    </div>

  </div>
</main>
