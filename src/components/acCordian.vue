<template>
  <div class="faq">
    <div class="faq-container">
      <div class="faq-header">
        <h1>Frequently Asked Questions</h1>
        <p>Here are some of our FAQs. If you have any other questions you’d like answered please feel free to email us.</p>
      </div>
      <hr>
      <div class="faq-content" v-for="item in items" :key="item.id">
        <div class="faq-title">
          <button @click="handleVisible(item.id)">
            <span>{{ item['faq-title'] }}</span>
            <img v-if="!isVisible[item.id]" src="../assets/images/icon-arrow.svg" alt="Expand"/>
            <img v-else src="../assets/images/icon-arrow-up.svg" alt="Collapse"/>
          </button>
        </div>
        <div class="faq-desc" v-if="isVisible[item.id]">
          <p>{{ item['content'] }}</p>
        </div>
        <hr>
      </div>
      <button class="btn-blue">More Info</button>
    </div>

  </div>
</template>

<script>
import { reactive } from 'vue';

export default {
  setup() {
    const items = [
      {
        id: 1,
        "faq-title": "What is Bookmark?",
        "content": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce tincidunt justo eget ultricies fringilla. Phasellus blandit ipsum quis quam ornare mattis."
      },
      {
        id: 2,
        "faq-title": "How can I request a new browser?",
        "content": "Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet. Vivamus luctus eros aliquet convallis ultricies. Mauris augue massa, ultricies non ligula. Suspendisse imperdiet."
      },
      {
        id: 3,
        "faq-title": "Is there a mobile app?",
        "content": "Sed consectetur quam id neque fermentum accumsan. Praesent luctus vestibulum dolor, ut condimentum urna vulputate eget. Cras in ligula quis est pharetra mattis sit amet pharetra purus. Sed sollicitudin ex et ultricies bibendum."
      },
      {
        id: 4,
        "faq-title": "What about other Chromium browsers?",
        "content": "Integer condimentum ipsum id imperdiet finibus. Vivamus in placerat mi, at euismod dui. Aliquam vitae neque eget nisl gravida pellentesque non ut velit."
      }
    ];

    // Initialize visibility state as an object
    const isVisible = reactive({});

    // Initialize isVisible object with false values for each item
    items.forEach(item => {
      isVisible[item.id] = false;
    });

    const handleVisible = (id) => {
      // Toggle visibility of the item by its id
      isVisible[id] = !isVisible[id];
    };

    return {
      items,
      isVisible,
      handleVisible
    };
  }
};
</script>

<style lang="scss">
@import '../assets/accordian.scss';
</style>    