<template>
  <calendar
    :event-array="validCalendarData"
    :sunday-first-day-of-week="false"
    calendar-locale="en-GB"
    calendar-timezone="Europe/London"
  />
</template>

<style>
</style>

<script>
import {
  Calendar
} from 'quasar-calendar'
export default {
  name: 'PageIndex',
  components: {
    Calendar
  },
  data () {
    return {
      validCalendarData: [

        // Multi events starting at the same time.
        {
          id: this.randomID(),
          summary: 'Event #1',
          description: 'Event #1 and #3 should be in one column.',
          start: {
            dateTime: '2019-02-11T11:00:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-11T12:30:00'
          }
        },
        {
          id: this.randomID(),
          summary: 'Event #2',
          description: 'Event #1 and #3 should be in one column.',
          start: {
            dateTime: '2019-02-11T11:00:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-11T12:30:00'
          }
        },
        {
          id: this.randomID(),
          summary: 'Event #3',
          description: 'Event #1 and #3 should be in one column.',
          start: {
            dateTime: '2019-02-11T11:00:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-11T12:30:00'
          }
        },

        // Wrapping test.
        {
          id: this.randomID(),
          summary: 'Some other test event',
          description: 'Some extra info goes here',
          start: {
            dateTime: '2019-02-12T11:00:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-12T12:30:00'
          }
        },
        {
          id: this.randomID(),
          summary: 'Some other test event',
          description: 'Some extra info goes here',
          start: {
            dateTime: '2019-02-12T12:00:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-12T13:00:00'
          }
        },
        {
          id: this.randomID(),
          summary: 'Some other test event',
          description: 'Some extra info goes here',
          start: {
            dateTime: '2019-02-12T12:30:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-12T13:30:00'
          }
        },
        {
          id: this.randomID(),
          summary: 'Some other test event',
          description: 'Some extra info goes here',
          start: {
            dateTime: '2019-02-12T13:00:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-12T14:00:00'
          }
        },

        // Testing how long after an event finishes it wraps correctly
        // End time of #1 and start time of #2 are identical
        {
          id: this.randomID(),
          summary: 'Some other test event',
          description: 'Some extra info goes here',
          start: {
            dateTime: '2019-02-13T12:30:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-13T13:30:00'
          }
        },
        {
          id: this.randomID(),
          summary: 'Some other test event',
          description: 'Some extra info goes here',
          start: {
            dateTime: '2019-02-13T13:30:00' // timezone embedded in dateTime
          },
          end: {
            dateTime: '2019-02-13T14:30:00'
          }
        }

      ]
    }
  },
  methods: {
    randomID () {
      return Math.floor((1 + Math.random()) * 0x10000)
        .toString(16)
        .substring(1)
    }
  }
}
</script>
