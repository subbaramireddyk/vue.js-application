<template>
  <section class="counter-section">
    <h3>Interactive Counter</h3>
    <div class="counter-display">
      <button @click="decrement" class="btn btn-secondary">-</button>
      <span class="counter-value" :key="count">{{ count }}</span>
      <button @click="increment" class="btn btn-primary">+</button>
    </div>
    <button @click="reset" class="btn btn-reset">Reset</button>
  </section>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Counter',
  setup() {
    const count = ref(0)

    const increment = () => {
      count.value++
    }

    const decrement = () => {
      count.value--
    }

    const reset = () => {
      count.value = 0
    }

    return {
      count,
      increment,
      decrement,
      reset
    }
  }
}
</script>

<style scoped>
.counter-section {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 40px;
  border-radius: 12px;
  text-align: center;
  margin-bottom: 40px;
  color: white;
}

.counter-section h3 {
  font-size: 2rem;
  margin-bottom: 30px;
}

.counter-display {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 30px;
  margin-bottom: 20px;
}

.counter-value {
  font-size: 4rem;
  font-weight: bold;
  min-width: 120px;
  animation: pulse 0.3s ease;
}

.btn {
  padding: 12px 30px;
  font-size: 1.1rem;
  font-weight: bold;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
}

.btn:active {
  transform: translateY(0);
}

.btn-primary {
  background: #42b883;
  color: white;
}

.btn-primary:hover {
  background: #35a372;
}

.btn-secondary {
  background: white;
  color: #667eea;
}

.btn-secondary:hover {
  background: #f0f0f0;
}

.btn-reset {
  background: rgba(255, 255, 255, 0.2);
  color: white;
  border: 2px solid white;
}

.btn-reset:hover {
  background: rgba(255, 255, 255, 0.3);
}

@media (max-width: 768px) {
  .counter-value {
    font-size: 3rem;
  }

  .counter-display {
    gap: 15px;
  }
}
</style>
