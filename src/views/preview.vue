<template>
  <div style="height:100%" id="iframewrap"></div>
  <!-- <iframe src="http://192.168.218.113:3000/#/" width="100%" height="100%" id="myFrame"></iframe> -->
</template>

<script>
export default {
  mounted() {
    this.$nextTick(() => {
      var iframe = document.createElement("iframe");
      iframe.src = "http://192.168.218.113:3000/#/";
      iframe.id = "myFrame";
      iframe.width = "100%";
      iframe.height = "100%";

      iframe.onload = function () {
        document.getElementById('myFrame').contentWindow.postMessage('getcolor', 'http://192.168.218.113:3000/#/');
      };
      document.getElementById("iframewrap").appendChild(iframe);
    })
  }
};
</script>