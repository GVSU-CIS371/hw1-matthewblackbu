<template>
<div>
  <Beverage :isIced="currentTemp === 'Cold'" />
  <ul>
    <li>
      <template v-for="temp in temps" :key="temp">
        <label>
          <input
            type="radio"
            name="temperature"
            :id="`r${temp}`"
            :value="temp"
            v-model="currentTemp"
          />
          {{ temp }}
        </label>
      </template>
      <div></div>
      <template v-for="base in bases" :key="base.id">
        <label>
          <input
            type="radio"
            name="basedrink"
            :id="`r${base.id}`"
            :value="base"
            v-model="currentBase"
          />
          {{ base.name }}
        </label>
      </template>
      <div></div>
      <template v-for="syrup in syrups" :key="syrup.id">
        <label>
          <input
            type="radio"
            name="basesyrup"
            :id="`r${syrup}`"
            :value="syrup"
            v-model="currentSyrup"
          />
          {{ syrup.name }}
        </label>
      </template>
      <div></div>
      <template v-for="creamer in creamers" :key="creamer.id">
        <label>
          <input
            type="radio"
            name="creamertype"
            :id="`r${creamer}`"
            :value="creamer"
            v-model="currentCream"
          />
          {{ creamer.name }}
        </label>
      </template>
    </li>
  </ul>
</div>
</template>

<script setup lang="ts">
import Beverage from './components/Beverage.vue';
import {temps,currentTemp,bases,currentBase,creamers,
  currentCream,syrups,currentSyrup,} from './stores/beverage';
</script>

<style lang="scss">
body,
html {
position: relative;
display: flex;
align-items: center;
justify-content: center;
height: 100%;
background-color: #6e4228;
background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
list-style: none;
}
</style>
