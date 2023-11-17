<template>
  <n-spin v-if="load.main"></n-spin>
  <div v-else>
    <n-card title="Вход" class="form-login">
      {{ user.data }}
      <n-form
        ref="formRef"
        :value="user.data"
        :rules="user.rules"
        size="medium"
      >
        <n-form-item
          v-for="(labelUser, userProperty) in user.labels"
          :key="userProperty"
          :label="labelUser"
        >
          <n-input v-model:value="user.data[userProperty]"></n-input>
        </n-form-item>
      </n-form>
    </n-card>
  </div>
</template>

<script lang="js">
import {defineComponent} from 'vue'
import UserLogin from '../models/user.login.model'
export default defineComponent({

    async created(){
        console.warn("CREATED")
        this.load.main = true
        this.load.main = false


    },

    data(){
        return {
            load: {
                main: false
            },
            user:  new UserLogin()
        };
    }


})
</script>
