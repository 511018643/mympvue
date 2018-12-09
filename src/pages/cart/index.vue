<template>
  <div>
    <ul>
      <li
        @longtap="delOne(index)"
        v-for="(item, index) in list"
        :key="index"
      >名字是: {{item.name}}-----技能是:{{item.skill}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "index",
  data: function() {
    return {
      list: [
        {name:"object.defineproperty",
        skill:"set和get"
        },
        {
          name: "张三",
          skill: "compile数据的解析器"
        },
        {
          name: "李四",
          skill: "watcher连接两者中的桥梁"
        },
        {
          name: "王五",
          skill: "observer观察者模式,变化了就触发set方法"
        }
      ]
    };
  },
  methods: {
    delOne(index) {
      wx.showModal({
        title: "提示",
        content: "这是一个模态弹窗",
        success: res => {
          if (res.confirm) {
            this.list.splice(index, 1);
          } else if (res.cancel) {
          }
        }
      });
    }
  }
};
</script>
