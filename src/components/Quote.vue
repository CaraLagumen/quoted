<template>
  <div class="col-sm-6 col-md-4 col-log-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["quotes"]
};
</script>

<style>
.panel-body {
  color: #6e6e6e;
  font-family: "Arizonia", cursive;
  font-size: 24px;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: #ffe2e2;
}
</style>
