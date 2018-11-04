<template>
  <linear-gradient :style="{flex: 1}" :colors="['#00cdac', '#8ddad5']">
    <status-bar
      barStyle="light-content"
      :translucent="true"
      backgroundColor="transparent"
    />
    <nb-container>
      <view :style="{flex: 40, justifyContent: 'center', alignItems: 'center'}">
        <image
          :source="require(`../../assets/images/logo-white.png`)"
          :style="{width:150}"
          resizeMode="contain"
        />
      </view>
      <view :style="{flex: 60, justifyContent: 'center', alignItems: 'center'}">
        <LoginButton />
      </view>
    </nb-container>
    <nb-spinner color="white" v-if="!loaded"></nb-spinner>
  </linear-gradient>
</template>

<script>
import { Dimensions, Platform, AsyncStorage, StatusBar } from "react-native";
import { Toast } from 'native-base';
import { NavigationActions } from 'vue-native-router';
import LinearGradient from 'react-native-linear-gradient';
import { LoginButton, AccessToken } from 'react-native-fbsdk';


import store from '../store';
export default {
  components: {
    LinearGradient,
    StatusBar,
    LoginButton
  },
  props: {
    navigation: {
      type: Object
    }
  },
  computed: {
    logging_in () {
      return store.state.logging_in;
    }
  },
  data: function() {
    return {
      emailValue: '',
      password: '',
      loaded: false
    };
  },
  methods: {
    // _onLoginFB (error, result) {
    //    if (error) {
    //       alert('Login failed with error: ' + result.error);
    //   } else if (result.isCancelled) {
    //       alert('Login was cancelled');
    //   } else {
    //       alert('Login was successful with permissions: ' 
    //           + result.grantedPermissions)
    //   }
    // },
    // _onLogoutFB () {
    //   alert('User logged out')
    // },
  }
};
</script>