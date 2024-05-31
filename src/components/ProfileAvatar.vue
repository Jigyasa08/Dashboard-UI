<template>
  <div class="avatar">
    <div class="avatar-image" :style="{ backgroundColor: color }"></div>
    <div class="avatar-content">
      <span class="avatar-name" :style="{ fontWeight: fontWeight }">{{
        name
      }}</span>
      <span class="avatar-message" :style="{ fontSize: fontSize }">{{
        message
      }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProfileAvatar",
  props: {
    name: {
      type: String,
      required: true,
    },
    message: {
      type: String,
      required: false,
      default: "",
    },
    color: {
      type: String,
      required: false,
      default: "#000",
    },
    fontWeight: {
      type: String,
      required: false,
      default: "bold",
    },
    fontSize: {
      type: String,
      required: false,
      default: "0.7em",
    },
  },
};
</script>

<style scoped>
.avatar {
  display: flex;
  align-items: center;
  margin-bottom: 10px;
}

.avatar-image {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  margin-right: 10px;
}

.avatar-content {
  display: flex;
  flex-direction: column;
}

.avatar-message {
  color: #888;
}
</style>
