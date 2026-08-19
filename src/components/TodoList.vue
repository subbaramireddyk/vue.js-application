<template>
  <section class="todo-section">
    <h3>Todo List</h3>
    <div class="todo-input-group">
      <input
        v-model="newTodo"
        @keyup.enter="addTodo"
        type="text"
        placeholder="Enter a new task..."
        class="todo-input"
      >
      <button @click="addTodo" class="btn btn-primary">Add</button>
    </div>

    <ul class="todo-list" v-if="todos.length > 0">
      <li
        v-for="(todo, index) in todos"
        :key="index"
        :class="{ completed: todo.completed }"
        class="todo-item"
      >
        <input
          type="checkbox"
          v-model="todo.completed"
          class="todo-checkbox"
        >
        <span class="todo-text">{{ todo.text }}</span>
        <button @click="removeTodo(index)" class="btn-delete">×</button>
      </li>
    </ul>
    <p v-else class="empty-message">No todos yet. Add one above!</p>
  </section>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'TodoList',
  setup() {
    const newTodo = ref('')
    const todos = ref([
      { text: 'Learn Vue.js', completed: true },
      { text: 'Build an amazing app', completed: false },
      { text: 'Deploy to OneStack Portal', completed: false }
    ])

    const addTodo = () => {
      if (newTodo.value.trim()) {
        todos.value.push({
          text: newTodo.value.trim(),
          completed: false
        })
        newTodo.value = ''
      }
    }

    const removeTodo = (index) => {
      todos.value.splice(index, 1)
    }

    return {
      newTodo,
      todos,
      addTodo,
      removeTodo
    }
  }
}
</script>

<style scoped>
.todo-section {
  background: #f8f9fa;
  padding: 40px;
  border-radius: 12px;
  margin-bottom: 40px;
}

.todo-section h3 {
  font-size: 2rem;
  margin-bottom: 20px;
  color: #35495e;
  text-align: center;
}

.todo-input-group {
  display: flex;
  gap: 10px;
  margin-bottom: 20px;
}

.todo-input {
  flex: 1;
  padding: 12px 20px;
  font-size: 1rem;
  border: 2px solid #ddd;
  border-radius: 8px;
  transition: border-color 0.3s ease;
}

.todo-input:focus {
  outline: none;
  border-color: #42b883;
}

.todo-list {
  list-style: none;
}

.todo-item {
  display: flex;
  align-items: center;
  gap: 15px;
  padding: 15px;
  background: white;
  border-radius: 8px;
  margin-bottom: 10px;
  transition: all 0.3s ease;
  animation: slideIn 0.3s ease;
}

.todo-item:hover {
  transform: translateX(5px);
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}

.todo-item.completed {
  opacity: 0.6;
}

.todo-item.completed .todo-text {
  text-decoration: line-through;
  color: #999;
}

.todo-checkbox {
  width: 20px;
  height: 20px;
  cursor: pointer;
}

.todo-text {
  flex: 1;
  font-size: 1.1rem;
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

.btn-primary {
  background: #42b883;
  color: white;
}

.btn-primary:hover {
  background: #35a372;
}

.btn-delete {
  background: #ff6b6b;
  color: white;
  border: none;
  width: 30px;
  height: 30px;
  border-radius: 50%;
  font-size: 1.5rem;
  line-height: 1;
  cursor: pointer;
  transition: all 0.3s ease;
  padding: 0;
}

.btn-delete:hover {
  background: #ff5252;
  transform: rotate(90deg);
}

.empty-message {
  text-align: center;
  color: #999;
  font-style: italic;
  padding: 20px;
}

@media (max-width: 768px) {
  .todo-input-group {
    flex-direction: column;
  }
}
</style>
