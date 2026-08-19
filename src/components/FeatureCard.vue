<template>
  <div class="feature-card">
    <h3>{{ emoji }} {{ title }}</h3>
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  name: 'FeatureCard',
  props: {
    emoji: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
.feature-card {
  flex: 1;
  min-width: 250px;
  padding: 30px;
  background: #f8f9fa;
  border-radius: 8px;
  text-align: center;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 25px rgba(66, 184, 131, 0.2);
}

.feature-card h3 {
  font-size: 1.5rem;
  margin-bottom: 10px;
  color: #35495e;
}

.feature-card p {
  color: #666;
}
</style>
