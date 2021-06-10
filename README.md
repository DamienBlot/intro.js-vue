# intro.js-vue

A Vue.js wrapper to use the Intro.js solution

## Install

```bash
npm install intro-js-vue
```

```vue
<script>
  import { Steps, Hints } from 'intro-js-vue';
</script>
```

Both `Steps` and `Hints` components currently display buttons that receive a prop "options", which are your steps or your hints to give to Intro.js as a JSON object.

## Implementation example

```vue
<template>
  <Steps :options="steps" />
  <Hints :options="hints" />
  <h1 classs="h1Class">Test</h1>
</template>

<script>
  import { Steps, Hints } from "intro-js-vue";
  export default {
    name: "Test",
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
      (this.steps = {
        steps: [
          {
            title: "Welcome",
            element: document.querySelector(".h1Class"),
            intro: "Etape 1",
          },
        ],
      }),
        (this.hints = {
          hints: [
            {
              hint: "First hint",
              element: document.querySelector(".h1Class"),
              hintPosition: "bottom-middle",
            },
          ],
        });
    },
  };
</script>
```
