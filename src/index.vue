<template>
  <root>
    <app-navigation></app-navigation>
  </root>
</template>


<script>
import React from "react";
import { StackNavigator, DrawerNavigator, navigationService } from "vue-native-router";
import { Root } from "native-base";
import LoginScreen from "./screens/login.vue";
// import SignupScreen from "./screen/Signup/index.vue";
import HomeScreen from "./screens/home.vue";
const Drawer = DrawerNavigator(
  {
    Home: { screen: HomeScreen },
  },
  {
    initialRouteName: "Home",
  }
);
const AppNavigation = StackNavigator(
  {
    Login: { screen: LoginScreen },
    Drawer: { screen: Drawer }
  },
  {
    initialRouteName: "Login",
    headerMode: "none"
  }
);
export default {
  components: { Root, AppNavigation }
};
</script> 