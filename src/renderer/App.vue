<template>
  <div id="app">
    <ToolBar>
      <DrawerBar>
        <transition name="page" mode="out-in">
          <router-view></router-view>
        </transition>
      </DrawerBar>
    </ToolBar>
  </div>
</template>

<script>
import DrawerBar from "./components/Navigations/DrawerBar";
import ToolBar from "./components/Navigations/ToolBar";

export default {
  name: 'eternal-process-daemon',
  components: {ToolBar, DrawerBar},
  mounted() {
    console.log("getCPUUsage:", process.getCPUUsage());
    //cpu操作位数
    console.log("arch:", process.arch);
    //环境变量
    console.log("env:", process.env);
  }
}
</script>

<style>
.page-enter-active, .page-leave-active {
  transition: all .2s
}

.page-enter, .page-leave-to {
  -webkit-transform: translateY(1.25rem);
  transform: translateY(1.25rem);
  opacity: 0
}

.page-enter-to .page-leave {
  -webkit-transform: translateY(0);
  transform: translateY(0);
  opacity: 1
}

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  width: 100%;
  height: 100%;
  background-color: #1E1E1E;
  /*box-shadow: 0.5rem 0.875rem 2.375rem rgba(39, 44, 49, .06), 0.0625rem 0.1875rem 0.5rem rgba(39, 44, 49, .03);*/
  user-select: none;
}

.RGB-ON {
  background: linear-gradient(124deg, #ff2400, #e81d1d, #e8b71d, #e3e81d, #1de840, #1ddde8, #2b1de8, #dd00f3, #dd00f3);
  color: #fff;
  background-size: 1800% 1800%;
  -webkit-animation: rainbow 15s ease infinite;
  -z-animation: rainbow 15s ease infinite;
  -o-animation: rainbow 15s ease infinite;
  animation: rainbow 15s ease infinite;
}

@-webkit-keyframes rainbow {
  0% {
    background-position: 0% 82%
  }
  50% {
    background-position: 100% 19%
  }
  100% {
    background-position: 0% 82%
  }
}

@-moz-keyframes rainbow {
  0% {
    background-position: 0% 82%
  }
  50% {
    background-position: 100% 19%
  }
  100% {
    background-position: 0% 82%
  }
}

@-o-keyframes rainbow {
  0% {
    background-position: 0% 82%
  }
  50% {
    background-position: 100% 19%
  }
  100% {
    background-position: 0% 82%
  }
}

@keyframes rainbow {
  0% {
    background-position: 0% 82%
  }
  50% {
    background-position: 100% 19%
  }
  100% {
    background-position: 0% 82%
  }
}
</style>
