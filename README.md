# intro.js-vue

A Vue.js wrapper to use the [Intro.js](https://introjs.com/) solution.
[See the module on NPM](https://www.npmjs.com/package/intro-js-vue).

## Install

```bash
npm install intro-js-vue
```

```vue
<script>
  import { Steps, Hints } from 'intro-js-vue';
</script>
```

## Note

Both `Steps` and `Hints` components currently display buttons that receive a prop "options", which are your steps or your hints to give to Intro.js as a JSON object.

## Implementation example

```vue
<template>
  <Steps :options="steps" />
  <Hints :options="hints" />
  <p>
    Intro.js logo
    <img src="https://introjs.com/img/social.png" alt="intro.js logo" width="300" />
  </p>
</template>

<script>
  import { Steps, Hints } from "intro-js-vue";
  export default {
    name: "Demo",
    components: {
      Steps,
      Hints,
    },
    data() {
      return {
        steps: null,
        hints: null,
      };
    },
    mounted() {
      this.steps = {
        steps: [
          {
            title: "Welcome",
            element: document.querySelector("p"),
            intro: "Etape 1",
          },
        ],
      };
      
      this.hints = {
        hints: [
          {
            hint: "First hint",
            element: document.querySelector("img"),
            hintPosition: "bottom-middle",
          },
        ],
      };
    },
  };
</script>
```
