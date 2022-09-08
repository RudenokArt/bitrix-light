<template>
 <br>
 <span class="text-info">{{StatusName}}</span>
</template>

<script>
  export default {
    props: {
      status: {type: String},
    },
    computed: {
      StatusName: function () {
        if (this.status == '1') {
          return 'новая';
        };
        if (this.status == '2') {
          return 'на рассмотрении';
        }
        if (this.status == '3') {
          return 'в работе';
        }
        if (this.status == '4') {
          return 'сдана на проверку';
        }
        if (this.status == '5') {
          return 'выполнена';
        }
        if (this.status == '6') {
          return 'отложена';
        }
        if (this.status == '7') {
          return 'отклонена';
        }
      },
    },
  };
</script>