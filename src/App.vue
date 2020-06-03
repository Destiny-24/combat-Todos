<template>
  <!DOCTYPE html>
  <html>
    <head>
      <title>TodoDemo</title>
    </head>
    <body>
      <div class="todoapp">
        <the-header />
        <Thelist />
        <TheFooter />
      </div>
    </body>
  </html>
</template>
<script>
import "@/assets/base.css";
import "@/assets/index.css";
import TheHeader from "@/components/TheHeader";
import Thelist from "@/components/TodoList";
import TheFooter from "@/components/TheFooter";
export default {
  components: {
    "the-header": TheHeader,
    Thelist,
    TheFooter
  }
};
</script>
