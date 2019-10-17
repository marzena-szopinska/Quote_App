<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.panel-body {
  font-family: "Arizonia", cursive;
  font-size: 24px;
  color: gray;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: rgba(255, 0, 0, 0.24);
}
</style>