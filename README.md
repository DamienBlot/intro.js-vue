# intro.js-vue

vue.js wrapper to use intro.js solution

## two components

```bash
npm install intro.js-vue
```

```vue
<script>
  import { Steps, Hints } from 'intro.js-vue';
</script>
```

Both components are buttons that allow you to give "options" to your
intro.js steps or hints.

exemple of implementation :

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
            element: document.querySelector("h1Class"),
            intro: "Etape 1",
          },
        ],
      }),
        (this.hints = {
          hints: [
            {
              hint: "First hint",
              element: document.querySelector("h1Class"),
              hintPosition: "bottom-middle",
            },
          ],
        });
    },
  };
</script>
```
