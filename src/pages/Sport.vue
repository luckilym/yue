<template>
	<div class="sports">
		<panel-list :sport-list="sportsList"></panel-list>
	</div>
</template>

<script>
import panelList from "@/components/panelList";
import data from '../../jsonData/sportList'
import { mapGetters } from "vuex";

export default {
  components: {
    panelList
  },
  data() {

    return {
      sportsList:data.data
    };
  },
  created() {
    if (this.sportsList.length == 0) {
      this.$store.dispatch("getSportsList");
    }
  },
  computed: {
    // ...mapGetters(["sportsList"])
  },
  mounted() {},
  methods: {}
};
</script>