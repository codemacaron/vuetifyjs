<template lang="pug">
  .scroll-table
    table
      thead
        tr
          th(width="100") 타이틀1
          th(width="100") 타이틀2
          th(width="100") 타이틀3
          th(width="150") 타이틀4
          th(width="50" v-bind:class="{active : checkListNum}") ⓒ
      tbody(style="height:100px")
        tr(v-for="item in content")
          td(width="100") {{ item.content1 }}
          td(width="100") {{ item.content2 }}
          td(width="100") {{ item.content3 }}
          td(:width="widhtchange(200)" colspan="2") {{ item.content4 }}
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      checkListNum: false,
      content: [
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        },
        {
          content1: "내용1",
          content2: "내용2",
          content3: "내용3",
          content4: "내용4"
        }
      ]
    };
  },
  methods: {
    widhtchange(props) {
      if (this.content.length > 3) {
        this.checkListNum = true;
        return props - 17;
      } else {
        this.checkListNum = false;
        return props;
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
* {
  box-sizing: border-box;
}

.scroll-table {
  width: 500px;
  overflow: auto;
}

.scroll-table table {
  border-collapse: collapse;
  border-spacing: 0;
}

.scroll-table th,
.scroll-table td {
  font-size: 13px;
}

.scroll-table thead tr {
  display: block;
  border-top: 1px solid #ccc;
  border-bottom: 1px solid #ccc;
  background: #dedfdf;
}

.scroll-table tbody tr {
  border-bottom: 1px solid #ccc;
}

.scroll-table thead th {
  padding: 4px 10px;
  border-left: 1px solid #eee;
}

.scroll-table thead th:first-of-type {
  border-left: 0 none;
}
.scroll-table thead th.active {
  padding-right: 27px;
}

.scroll-table tbody {
  display: block;
  width: 100%;
  overflow: auto;
}

.scroll-table tbody td:last-of-type {
  background: #dedfdf;
}
</style>
