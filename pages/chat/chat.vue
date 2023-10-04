<template>
  <div class="dialog">
    <div class="messages">
      <div v-for="(message, index) in messages" :key="index" class="message" :class="{ 'user-message': message.type === 'user', 'assistant-message': message.type === 'assistant' }">
        <p class="content">{{ message.content }}</p>
      </div>
    </div>
    <div class="input">
      <input type="text" v-model="userInput" @keydown.enter="sendMessage" placeholder="请输入消息" />
      <button @click="sendMessage">发送</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userInput: '',
      messages: []
    };
  },
  methods: {
    sendMessage() {
      if (this.userInput.trim() !== '') {
        this.messages.push({
          type: 'user',
          content: this.userInput.trim()
        });
        // 根据用户输入的内容进行相应的处理
        // ...
        this.messages.push({
          type: 'assistant',
          content: '收到你的消息啦！'
        });
        this.userInput = '';
      }
    }
  }
};
</script>

<style lang="scss">
.dialog {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background-color: #f5f5f5;
  padding: 10px;
  box-sizing: border-box;
}

.messages {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  overflow-y: auto;
}

.message {
  display: inline-block;
  background-color: #e6f2ff;
  padding: 10px;
  margin-bottom: 5px;
  border-radius: 5px;
  max-width: 70%;
}

.message.user-message {
  align-self: flex-end;
  background-color: #e0e0e0;
  color: #fff;
}

.message.assistant-message {
  align-self: flex-start;
}

.message .content {
  margin: 0;
}

.input {
  display: flex;
  align-items: center;
  margin-top: 10px;
}

.input input {
  flex: 1;
  padding: 10px;
  border-radius: 5px;
  border: 1px solid #ccc;
}

.input button {
  padding: 10px 20px;
  margin-left: 10px;
  background-color: #007bff;
  color: #fff;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

@media (max-width: 768px) {
  .dialog {
    padding: 5px;
  }
  
  .message {
    max-width: 100%;
  }
  
  .input {
    margin-top: 5px;
  }
}
</style>