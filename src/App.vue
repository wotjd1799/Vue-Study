<template>
  <div id="app">
    <Header/>
    <Contents/>
    <Input/>
  </div>
</template>

<script>
import Header from './components/TodoHeader'
import Contents from './components/TodoContents'
import Input from './components/TodoInput'
export default {
  name: 'App',
  components: {
    Header,
    Contents,
    Input
  }
}
</script>

<style>
#app {
  margin: 0px auto;
  margin-top: 150px;
  width: 600px;
  height: 700px;
  display: flex;
  flex-direction: column;
  align-items: center;
  border-radius: 10px;
  box-shadow: 0 0 5px #888;
}
</style>
