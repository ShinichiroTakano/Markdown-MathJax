<template>
  <div>
    <div class="p-block-ttl">output</div>
    <div class="p-block-console-inner">
      <p>id mpg cylinders displacement horsepower weight acceleration \ 101 204 29.8 4 89.0 62.000000 1845.0 15.3 18 40 28.1 4 141.0 80.000000 3230.0 20.4 20 42 19.0 4 122.0 85.000000 2310.0 18.5 42 86 22.0 6 232.0 112.000000 2835.0 14.7 7 19 11.0 8 350.0 180.000000 3664.0 11.0 129 262 23.5 6 173.0 110.000000 2725.0 12.6 25 50 19.8 6 200.0 85.000000 2990.0 18.2 17 39 24.5 4 98.0 60.000000 2164.0 22.1 24 48 23.0 4 151.0 101.297436 3035.0 20.5 61 123 21.5 4 121.0 110.000000 2600.0 12.8 57 117 30.0 4 88.0 76.000000 2065.0 14.5 180 359 35.0 4 72.0 69.000000 1613.0 18.0 id mpg cylinders displacement horsepower weight acceleration \ 101 204 29.8 4 89.0 62.000000 1845.0 15.3 18 40 28.1 4 141.0 80.000000 3230.0 20.4 20 42 19.0 4 122.0 85.000000 2310.0 18.5 42 86 22.0 6 232.0 112.000000 2835.0 14.7 7 19 11.0 8 350.0 180.000000 3664.0 11.0 129 262 23.5 6 173.0 110.000000 2725.0 12.6 25 50 19.8 6 200.0 85.000000 2990.0 18.2 17 39 24.5 4 98.0 60.000000 2164.0 22.1 24 48 23.0 4 151.0 101.297436 3035.0 20.5 61 123 21.5 4 121.0 110.000000 2600.0 12.8 57 117 30.0 4 88.0 76.000000 2065.0 14.5 180 359 35.0 4 72.0 69.000000 1613.0 18.0</p>
    </div>
  </div>
</template>
<script>
export default {
  
}
</script>
<style lang="scss" scoped>
$color-user: #1F3964;
.p-block-ttl {
  background-color: $color-user;
  color: #fff;
  height: 35px;
  padding-left: 20px;
  font-weight: normal;
  border-radius: 8px 8px 0 0;
  display: flex;
  align-items: center;
}
.p-block-console-inner {
  overflow-y: scroll;
  padding: 20px;
  height: 100%;
}
</style>
