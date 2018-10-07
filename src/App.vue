<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>
<script>
import { mockLogin } from '@/api'
export default {
  name: 'app',
  beforeCreate() {
    const userMap = {
      "gmc": "123456",
      "ss": "123456",
      "trunks": "123456",
      "DDDDD": "DD2018",
      "EE:DY02": "123456",
      "swgyd":"123456"
    }
    mockLogin('swgyd', '123456').then(res => {
      const data = res.data
      document.cookie = 'Himall-SellerManager = ' + data.userId
    })
  }
}

</script>
