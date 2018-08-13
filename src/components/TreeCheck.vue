<template lang="pug">
div(style="text-align:center")
    el-form
        el-form-item(label="name")
            el-tree(
                :data="treeData"
                show-checkbox ref="tree"
                node-key="kindid"
                :default-expanded-keys="[2, 3]"
                :default-checked-keys="[5]"
                :props="defaultProps"
            )
    el-button(@click="getCheckedNodes") node
    el-button(@click="getCheckedKeys") key
    br
    label {{test}}
</template>

<script>
export default {
  data() {
    return {
      treeData: [
        {
          id: 1,
          kindid: 1,
          label: "一级 1",
          children: [
            {
              id: 4,
              kindid: 2,
              label: "二级 1-1",
              children: [
                {
                  id: 9,
                  kindid: 3,
                  label: "三级 1-1-1"
                },
                {
                  id: 10,
                  kindid: 4,
                  label: "三级 1-1-2"
                }
              ]
            }
          ]
        },
        {
          id: 2,
          kindid: 5,
          label: "一级 2",
          children: [
            {
              id: 5,
              kindid: 6,
              label: "二级 2-1"
            },
            {
              id: 6,
              kindid: 7,
              label: "二级 2-2"
            }
          ]
        },
        {
          id: 3,
          kindid: 8,
          label: "一级 3",
          children: [
            {
              id: 7,
              kindid: 9,
              label: "二级 3-1"
            },
            {
              id: 8,
              kindid: 10,
              label: "二级 3-2"
            }
          ]
        }
      ],
      defaultProps: {
        children: "children",
        label: "label"
      },
      test: ""
    };
  },
  methods: {
    getCheckedNodes: function() {
      console.log(this.$refs.tree.getCheckedNodes());
      this.test = this.$refs.tree.getCheckedNodes().toString();
    },
    getCheckedKeys: function() {
      console.log(this.$refs.tree.getCheckedKeys());
      this.test = this.$refs.tree.getCheckedKeys().toString();
    }
  }
};
</script>