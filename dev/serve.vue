<template>
  <div id="app">
    <h1 class="card-demo">
      Une fleur:
      <img
        class="card-image"
        src="https://www.elle.be/fr/wp-content/uploads/2020/02/fleur.jpg"
        alt=""
      />
    </h1>

    <Steps :options="steps" />
	<Hints :options="hints" />
  </div>
</template>

<script>
import { defineComponent } from "vue";
import { Steps, Hints } from "@/entry";

export default defineComponent({
  name: "ServeDev",
  components: { 
    Steps,
	Hints
  },
	data: function() {
    return {
      steps: null,
	  hints: null,
    }
  },
	mounted() {
		this.steps = {
			steps: [
				{
					title: 'Welcome !',
					intro: 'Etape 1',
				},
				{
					element: document.querySelector('.card-demo'),
					intro: 'Etape 2',
				},
				{
					title: 'Bye !',
					element: document.querySelector('.card-image'),
					intro: '<img src="https://www.nawpic.com/media/2020/baby-yoda-nawpic-25.jpg" alt="" width="200" />',
				}
			]
		}
		this.hints = {
			hints: [
				{ hint: 'First hint', element: document.querySelector('.card-demo'), hintPosition : 'bottom-left' },
				{ hint: 'Second hint', element: document.querySelector('.card-image'), hintAnimation: false }
			]
		}
	},
});
</script>
