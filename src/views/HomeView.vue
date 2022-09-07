<template>
  <div class="container">
    <div class="row border-bottom" v-for="(task, index) in taskList">
      <div class="col-lg-1 col-md-2 col-sm-4">
        {{task.id}}/{{task.status}}
      </div>
      <div class="col-lg-2 col-md-4 col-sm-8">
        {{normalTime(task.createdDate)}}
      </div>
      <div class="col-lg-9 col-md-6 col-sm-12">
        {{task.title}}
      </div>
    </div>
  </div>
  {{taskList[0]}}
</template>

<script>
  export default {
    data () {
      return {
        taskList: [],
      };
    },
    methods: {
      normalTime: function (time) {
        var arr = time.split('T');
        return arr[0]+' '+arr[1];
      },
      GetTasksList: async function () {
        var queryString = new URLSearchParams();
        queryString.set('order[ID]', 'desc');
        var response = await $.get(this.$store.state.apiUrl+'tasks.task.list.json?'+queryString.toString());
        this.taskList = response.result.tasks;
      }
    },
    mounted: function () {
      this.GetTasksList();
    },
  };
</script>

