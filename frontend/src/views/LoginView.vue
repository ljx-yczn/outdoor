http://localhost:5173/login<template>
  <div class="login">
    <div class="login-card">
      <h2>用户登录</h2>
      <form @submit.prevent="handleLogin">
        <div class="form-item">
          <input v-model="form.username" type="text" placeholder="请输入用户名" required />
        </div>
        <div class="form-item">
          <input v-model="form.password" type="password" placeholder="请输入密码" required />
        </div>
        <button class="login-btn" type="submit" :disabled="loading">
          {{ loading ? '登录中...' : '登录' }}
        </button>
      </form>
      <p v-if="errorMsg" class="error">{{ errorMsg }}</p>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'
import { useRouter } from 'vue-router'
import request from '@/api/request'

const router = useRouter()
const loading = ref(false)
const errorMsg = ref('')

const form = reactive({
  username: '',
  password: ''
})

const handleLogin = async () => {
  errorMsg.value = ''
  loading.value = true
  try {
    const res = await request.post('/login', {
      username: form.username,
      password: form.password
    })
    localStorage.setItem('token', res.token)
    router.push('/')
  } catch (e) {
    errorMsg.value = '登录失败，请检查用户名和密码'
  } finally {
    loading.value = false
  }
}
</script>

<style scoped>
.login {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  background: #f0f2f5;
}

.login-card {
  background: #fff;
  padding: 40px;
  border-radius: 8px;
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
  width: 360px;
}

.login-card h2 {
  text-align: center;
  margin-bottom: 24px;
  color: #333;
}

.form-item {
  margin-bottom: 16px;
}

.form-item input {
  width: 100%;
  padding: 10px 12px;
  border: 1px solid #dcdfe6;
  border-radius: 4px;
  font-size: 14px;
  box-sizing: border-box;
  outline: none;
  transition: border-color 0.2s;
}

.form-item input:focus {
  border-color: #409eff;
}

.login-btn {
  width: 100%;
  padding: 10px;
  background: #409eff;
  color: #fff;
  border: none;
  border-radius: 4px;
  font-size: 16px;
  cursor: pointer;
  transition: background 0.2s;
}

.login-btn:hover {
  background: #66b1ff;
}

.login-btn:disabled {
  background: #a0cfff;
  cursor: not-allowed;
}

.error {
  color: #f56c6c;
  font-size: 13px;
  text-align: center;
  margin-top: 12px;
}
</style>
