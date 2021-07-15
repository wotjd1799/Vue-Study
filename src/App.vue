<template>
  <div id="app">
    <Header/>
    <Input/>
    <Contents/>
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
    Input,
    Contents
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
  box-shadow: 0 0 25px 5px rgba(0, 0, 0, 0.08);
}
</style>
