<template>
  <div id="app">
    <header>
      <h1>{{ title }}</h1>
      <p class="subtitle">{{ subtitle }}</p>
    </header>

    <main class="container">
      <section class="hero">
        <h2>{{ heroTitle }}</h2>
        <p>{{ heroDescription }}</p>
      </section>

      <Counter />

      <TodoList />

      <section class="features">
        <FeatureCard
          v-for="feature in features"
          :key="feature.emoji"
          :emoji="feature.emoji"
          :title="feature.title"
          :description="feature.description"
        />
      </section>
    </main>

    <footer>
      <p>Deployed on OneStack Portal | Built with Vue.js {{ vueVersion }}</p>
    </footer>
  </div>
</template>

<script>
import { ref } from 'vue'
import Counter from './components/Counter.vue'
import TodoList from './components/TodoList.vue'
import FeatureCard from './components/FeatureCard.vue'

export default {
  name: 'App',
  components: {
    Counter,
    TodoList,
    FeatureCard
  },
  setup() {
    const title = ref('Welcome to OneStack Portal')
    const subtitle = ref('Vue.js Application Example')
    const heroTitle = ref('Reactive. Component-Based. Modern.')
    const heroDescription = ref('This Vue.js application demonstrates reactive data binding, event handling, and component architecture.')
    const vueVersion = ref('3.x')

    const features = ref([
      {
        emoji: '⚡',
        title: 'Reactive Data',
        description: 'Automatic UI updates with data changes'
      },
      {
        emoji: '🎯',
        title: 'Event Handling',
        description: 'Simple and intuitive event listeners'
      },
      {
        emoji: '🔄',
        title: 'Two-Way Binding',
        description: 'Seamless data synchronization'
      },
      {
        emoji: '📦',
        title: 'Component System',
        description: 'Reusable and maintainable components'
      }
    ])

    return {
      title,
      subtitle,
      heroTitle,
      heroDescription,
      vueVersion,
      features
    }
  }
}
</script>
