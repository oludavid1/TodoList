<template id="body">
    <div id="Todo">
        <h1>TodoList</h1>
        <input v-model="newTodo" @keyup.enter="addTodo">
        <button @click="addTodo">AddTodo</button>
        <ol>
            <li v-for="(todo, index) in todos" :key="index">
                {{ todo }}
                <button @click="removeTodo(index)">Remove</button>
            </li>
        </ol>
        <TodoApp />rty
        
    </div>
</template>

<script>


export default {
    data() {
        return {
            todos: [],
            newTodo: ''
        };
    },
    methods: {
        addTodo() {
            if (this.newTodo.trim() !== '') {
                this.todos.push(this.newTodo);
                this.newTodo = '';
            }
        },
        removeTodo(index) {
            this.todos.splice(index, 1);
        }
    }
}
</script>

<style scoped>
    #Todo{
        max-width: 400px;
        margin: 0 auto;
        padding: 20px;
        background-image: linear-gradient(62deg,rgba(7, 86, 160, 0.973) 13%, rgba(255, 122, 151, 0.5) 4%), linear-gradient(44deg,rgba(0, 43, 99, 0.079) 39%, rgba(242, 140, 143, 0.5) 18%), linear-gradient(118deg,rgba(84, 202, 242, 0.031) 40%, rgba(247, 155, 187, 0.5) 54%), linear-gradient(58deg,rgba(90, 90, 237, 0.161) 83%, rgba(249, 156, 142, 0.5) 23%);
        background-blend-mode: normal, lighten, multiply, hard-light;
        border-radius:8px;
        overflow: hidden;
    }
    li
    {
        color: black;
        list-style: none;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 5px;
        display: flex;
    }
    button
    {
        background-image: linear-gradient(62deg,rgba(7, 86, 160, 0.973) 13%, rgba(255, 122, 151, 0.5) 4%), linear-gradient(44deg,rgba(0, 43, 99, 0.079) 39%, rgba(242, 140, 143, 0.5) 18%), linear-gradient(118deg,rgba(84, 202, 242, 0.031) 40%, rgba(247, 155, 187, 0.5) 54%), linear-gradient(58deg,rgba(90, 90, 237, 0.161) 83%, rgba(249, 156, 142, 0.5) 23%);
        background-blend-mode: normal, lighten, multiply, hard-light;
    }
    input
    {
        width: 80%;
        outline: none;
        border: none;
        border-bottom: 1px solid black;
        background: transparent;
        height: 5vh;
    }
</style>

<!-- <template>
    <div class="weather-app">
      <h1>Vue Weather App</h1>
      <div v-if="loading">Loading...</div>
      <div v-else>
        <div v-if="error" class="error">{{ error }}</div>
        <div v-else>
          <div class="weather-card">
            <h2>{{ weatherData.name }}</h2>
            <div class="weather-info">
              <div class="weather-icon">
                <img :src="'http://openweathermap.org/img/wn/' + weatherData.weather[0].icon + '.png'" alt="Weather Icon">
              </div>
              <div class="weather-details">
                <p>{{ weatherData.weather[0].main }}</p>
                <p>Temperature: {{ weatherData.main.temp }}°C</p>
                <p>Humidity: {{ weatherData.main.humidity }}%</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        loading: true,
        error: null,
        weatherData: null,
      };
    },
    mounted() {
      this.fetchWeatherData();
    },
    methods: {
      fetchWeatherData() {
        // Replace 'YOUR_API_KEY' with your actual API key
        const apiKey = 'YOUR_API_KEY';
        const apiUrl = `https://api.openweathermap.org/data/2.5/weather?q=London,uk&units=metric&appid=${apiKey}`;
  
        fetch(apiUrl)
          .then((response) => response.json())
          .then((data) => {
            this.weatherData = data;
            this.loading = false;
          })
          .catch(() => {
            this.error = 'Failed to fetch weather data.';
            this.loading = false;
          });
      },
    },
  };
  </script>
  
  <style scoped>
  .weather-app {
    text-align: center;
  }
  
  .error {
    color: red;
  }
  
  .weather-card {
    display: inline-block;
    padding: 20px;
    background-color: #f0f0f0;
    border-radius: 5px;
    margin-top: 20px;
  }
  
  .weather-info {
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .weather-icon img {
    width: 50px;
  }
  
  .weather-details {
    margin-left: 20px;
    text-align: left;
  }
  </style> -->
  