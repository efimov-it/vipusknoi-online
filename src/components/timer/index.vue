<template>
    <div class="timer">
        <div class="timer_counter">
            <div class="timer_counter-number">
                 <div class="blue-wrapper timer_counter-number-a">{{days[0]}}</div>
                 <div class="blue-wrapper timer_counter-number-b">{{days[1]}}</div>
            </div>
        </div>
        <div class="timer_counter">
            <div class="timer_counter-number">
                 <div class="blue-wrapper timer_counter-number-a">{{hours[0]}}</div>
                 <div class="blue-wrapper timer_counter-number-b">{{hours[1]}}</div>
            </div>
        </div>
        <div class="timer_counter">
            <div class="timer_counter-number">
                 <div class="blue-wrapper timer_counter-number-a">{{minutes[0]}}</div>
                 <div class="blue-wrapper timer_counter-number-b">{{minutes[1]}}</div>
            </div>
        </div>
        <div class="timer_counter">
            <div class="timer_counter-number">
                 <div class="blue-wrapper timer_counter-number-a">{{seconds[0]}}</div>
                 <div class="blue-wrapper timer_counter-number-b">{{seconds[1]}}</div>
            </div>
        </div>
    </div>
</template>

<script>
import './timer.scss'

function getDaysDiff (time) {
    return parseInt(time/1000/60/60/24)
}
function getHoursDiff (time) {
    return parseInt((time/1000/60/60/24 - parseInt(time/1000/60/60/24)) * 24)
}
function getMinutesDiff (time) {
    return parseInt((time/1000/60/60 - parseInt(time/1000/60/60)) * 60)
}
function getSecondsDiff (time) {
    return parseInt((time/1000/60 - parseInt(time/1000/60)) * 60)
}
export default {
    props: ['dateTime'],
    data () {
        return {
            days: [0,0],
            hours: [0,0],
            minutes: [0,0],
            seconds: [0,0]
        }
    },
    created () {
        const interval = setInterval(()=> {
            const timeDiff = new Date(this.dateTime) - new Date();

            if (timeDiff <= 0) {
                clearInterval(interval);
                return
            }

            const days = getDaysDiff(timeDiff).toString().split(''),
                  hours = getHoursDiff(timeDiff).toString().split(''),
                  minutes = getMinutesDiff(timeDiff).toString().split(''),
                  seconds = getSecondsDiff(timeDiff).toString().split('');

            if(days.length == 1) days.splice(0, 0, '0');
            if(hours.length == 1) hours.splice(0, 0, '0');
            if(seconds.length == 1) seconds.splice(0, 0, '0');
            if(minutes.length == 1) minutes.splice(0, 0, '0');

            this.days = days;
            this.hours = hours;
            this.minutes = minutes;
            this.seconds = seconds;
        }, 1000);
    }
}
</script>