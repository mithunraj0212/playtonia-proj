<template>
  <v-card class="body-1">
    <p>
      <span class="title">Id:</span>
      {{msg.id}}
    </p>
    <p>
      <span class="title">Userid:</span>
      {{msg.userId}}
    </p>
    <p>
      <span class="title">Completed:</span>
      {{msg.completed}}
    </p>
    <p>
      <span class="title">Title:</span>
      {{msg.title}}
    </p>
  </v-card>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class Card extends Vue {
  @Prop() private msg!: string;
}
</script>

<style>
.v-card {
  padding: 10px 15px;
  margin-bottom: 20px;
  font-family: sans-serif;
  transition: all 200ms ease-in-out !important;
} 
.v-card:hover{
  transform: scale(1.05);
}
</style>