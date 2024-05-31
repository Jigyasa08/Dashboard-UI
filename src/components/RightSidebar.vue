<template>
  <div class="side-box">
    <section class="popular-products">
      <h3>Popular Product</h3>
      <ul>
        <li v-for="product in popularProducts" :key="product.name">
          <ProfileAvatar
            :name="product.name"
            :message="product.price"
            :color="product.color"
          />
        </li>
      </ul>
    </section>
    <section class="chat">
      <h3>Chat</h3>
      <ul>
        <li v-for="chat in chats" :key="chat.name">
          <ProfileAvatar
            :name="chat.name"
            :message="chat.message"
            :color="chat.color"
          />
        </li>
      </ul>
    </section>
  </div>
</template>

<script>
import ProfileAvatar from "./ProfileAvatar.vue";

export default {
  name: "RightSidebar",
  components: {
    ProfileAvatar,
  },
  data() {
    return {
      popularProducts: [
        { name: "Gadget Converter", price: "$250", color: "#1f77b4" },
        { name: "Lens Camera", price: "$50", color: "#ff7f0e" },
        { name: "Airpods", price: "$100", color: "#2ca02c" },
        { name: "Macbook", price: "$999", color: "#d62728" },
      ],
      chats: [
        { name: "Debra Young", message: "How's my product?", color: "#1f77b4" },
        {
          name: "Dorothy Collins",
          message: "How was the meeting",
          color: "#ff7f0e",
        },
        {
          name: "Chris Jordan",
          message: "How employee performance",
          color: "#2ca02c",
        },
        {
          name: "Denise Murphy",
          message: "How was the meeting",
          color: "#d62728",
        },
      ],
    };
  },
};
</script>

<style scoped>
.side-box {
  background-color: white;
  border-radius: 5px;
  padding: 20px;
  margin-top: 10px;
}

.popular-products,
.chat {
  margin-bottom: 50px;
}

.popular-products h3,
.chat h3 {
  margin-bottom: 10px;
}

.popular-products ul,
.chat ul {
  list-style: none;
  padding: 0;
}

.popular-products li,
.chat li {
  margin-bottom: 10px;
}

.popular-products li:last-child,
.chat li:last-child {
  margin-bottom: 0;
}
</style>
