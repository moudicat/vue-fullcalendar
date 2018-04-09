<template>
  <div>
  	<p>
  		Here is the demo of vue-fullcalendar, no jquery fullcalendar.js required!
  	</p>
    <full-calendar class="test-fc" :events="fcEvents" 
      first-day='1' locale="zh-cn"
      @changeMonth="changeMonth"
      @eventClick="eventClick"
      @dayClick="dayClick"
      @moreClick="moreClick">
        
    </full-calendar>
  </div>
</template>

<script>
let demoEvents = [
    {
      title    : 'Sunny 725-727',
      start    : '2018-02-25',
      end      : '2018-02-27',
      cssClass : 'family'
    },
    {
      title : 'Lunfel 726-727',
      start : '2018-02-26',
      end : '2018-02-27',
      cssClass : ['home', 'work']
    },
    {
      title : 'Lunfel 2/27-2/28',
      start : '2018-02-27',
      end : '2018-02-28'
    },
    {
        title : 'Lunfel 2/27-2/28',
        start : '2018-02-27',
        end : '2018-02-28'
    },
    {
        title : 'Lunfel 2/27-2/28',
        start : '2018-02-27',
        end : '2018-02-28'
    },
    {
        title : 'Lunfel 2/26-3/05',
        start : '2018-02-26',
        end : '2018-03-05'
    },
    {
        title : 'Lunfel 1/27-1/28',
        start : '2018-01-27',
        end : '2018-01-28'
    },
    {
        title : 'Lunfel 1/27-2/2',
        start : '2018-01-27',
        end : '2018-02-02'
    },
    {
        title : 'Lunfel 3/27-3/28',
        start : '2018-03-27',
        end : '2018-03-28'
    },
  ];

export default {
	data () {
		return {
            name:'Sunny!',
            fcEvents : []
        }
	},
  mounted() {
    setTimeout(() => {
      this.fcEvents.push(...demoEvents);
    }, 2000);
  },
  methods : {
    'changeMonth' (start, end, current) {
      console.log('changeMonth', start.format(), end.format(), current.format())
    },
    'eventClick' (event, jsEvent, pos) {
       console.log('eventClick', event, jsEvent, pos)
    },
    'dayClick' (day, jsEvent) {
      console.log('dayClick', day, jsEvent)
    },
    'moreClick' (day, events, jsEvent) {
      console.log('moreCLick', day, events, jsEvent)
    }
  },
  components : {
    'full-calendar' : require('src/fullCalendar')
  }
}
</script>
<style lang='scss'>
  .app{
    color:green;
  }
</style>


<style>
  *, *:after, *:before {
    box-sizing: border-box;
  }
</style>
