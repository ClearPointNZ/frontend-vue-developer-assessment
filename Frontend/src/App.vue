<script setup>
import { ref, onMounted } from 'vue'

const description = ref('')
const items = ref([])

onMounted(() => {
  // todo
})

const handleDescriptionChange = (event) => {
  // todo
}

async function getItems() {
  try {
    alert('todo')
  } catch (error) {
    console.error(error)
  }
}

async function handleAdd() {
  try {
    alert('todo')
  } catch (error) {
    console.error(error)
  }
}

function handleClear() {
  description.value = ''
}

async function handleMarkAsComplete(item) {
  try {
    alert('todo')
  } catch (error) {
    console.error(error)
  }
}
</script>

<template>
  <main class="App">
    <div class="container">
      <div class="row">
        <div class="col">
          <img src="clearPointLogo.png" class="img-fluid rounded" />
        </div>
      </div>
      <div class="row">
        <div class="col">
          <div class="alert alert-success">
            <h4 class="alert-heading">Todo List App</h4>
            Welcome to the ClearPoint frontend technical test. We like to keep things simple, yet clean so your task(s)
            are as follows:
            <br />
            <br />
            <ol className="list-left">
              <li>Add the ability to add (POST) a Todo Item by calling the backend API</li>
              <li>Display (GET) all the current Todo Items in the below grid and display them in any order you wish</li>
              <li>
                Bonus points for completing the 'Mark as completed' button code for allowing users to update and mark a
                specific Todo Item as completed and for displaying any relevant validation errors/ messages from the API
                in the UI
              </li>
              <li>Feel free to add unit tests and refactor the component(s) as best you see fit</li>
            </ol>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col">
          <div class="container">
            <h1>Add Item</h1>
            <div class="row mb-3">
              <label class="col col-form-label form-label col-sm-2">Description</label>
              <div class="col col-md-6">
                <input
                  class="form-control"
                  type="text"
                  placeholder="Enter description..."
                  :value="description"
                  @input="handleDescriptionChange"
                />
              </div>
            </div>
            <div class="row mb-3 offset-md-2">
              <div class="hstack gap-2">
                <button type="button" class="btn btn-primary" @click="handleAdd">Add Item</button>
                <button type="button" class="btn btn-secondary" @click="handleClear">Clear</button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <br />
      <div class="row">
        <div class="col">
          <h1>
            Showing {{ items.length }} Item(s)
            <button type="button" class="pull-right btn btn-primary" @click="getItems">Refresh</button>
          </h1>
          <table class="table table-striped table-bordered table-hover">
            <thead>
              <tr>
                <th>Id</th>
                <th>Description</th>
                <th>Action</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in items" :key="item.id">
                <td>{{ item.id }}</td>
                <td>{{ item.description }}</td>
                <td>
                  <button type="button" class="btn btn-warning btn-sm" @click="() => handleMarkAsComplete(item)">
                    Mark as completed
                  </button>
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
    <footer className="page-footer font-small teal pt-4">
      <div className="footer-copyright text-center py-3">
        © 2021 Copyright:
        <a href="https://clearpoint.digital" target="_blank" rel="noreferrer"> clearpoint.digital </a>
      </div>
    </footer>
  </main>
</template>

<style scoped>
.App {
  text-align: center;
}

.list-left {
  text-align: left;
}

@media (prefers-reduced-motion: no-preference) {
  .App-logo {
    animation: App-logo-spin infinite 20s linear;
  }
}

@keyframes App-logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}
</style>
