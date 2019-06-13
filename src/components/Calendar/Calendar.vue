<template>
	<div id="app">
		<calendar-view
      :events="events"
      :show-date="showDate"
      :time-format-options="{hour: 'numeric', minute:'2-digit'}"
      :show-event-times="showEventTimes"
			class="theme-han holiday-us-traditional holiday-us-official">
			<calendar-view-header
				slot="header"
				slot-scope="t"
				:header-props="t.headerProps"
				@input="setShowDate" />
		</calendar-view>
	</div>
</template>
<script>
	import { CalendarView, CalendarViewHeader } from "vue-simple-calendar"
	// The next two lines are processed by webpack. If you're using the component without webpack compilation,
	// you should just create <link> elements for these. Both are optional, you can create your own theme if you prefer.
	require("./style.css")
	require("vue-simple-calendar/static/css/holidays-us.css")

	export default {
		name: 'app',
		data: function() {
      return { 
        showDate: new Date(),
        showEventTimes: true,

      }
    },
    props: {
      events: []
    },
		components: {
			CalendarView,
			CalendarViewHeader,
		},
		methods: {
			setShowDate(d) {
				this.showDate = d;
			},
		}
	}
</script>
<style>
	#app {
		font-family: 'Avenir', Helvetica, Arial, sans-serif;
		color: #2c3e50;
		height: 67vh;
		width: 90vw;
		margin-left: auto;
		margin-right: auto;
	}
</style>