<template>
    <div id="clock">
        <p class="date">{{ date }}</p>
        <p class="time">{{ time }}</p>
    </div>
</template>

<script>
import { setInterval } from 'timers';
export default {
    name: 'ClockWidget',
    data() {
        return {
            days: ['SUN', 'MON', 'TUE', 'WED', 'THU', 'FRI', 'SAT'],
            date: '',
            time: ''
        }
    },
    created() {
        this.updateTime();
        this.interval = setInterval(() => this.updateTime(), 1000);
    },
    methods: {
        updateTime() {
            
            var date = new Date();
            this.time = this.addZero(date.getHours(), 2) + ':' + this.addZero(date.getMinutes(), 2) + ':' + this.addZero(date.getSeconds(), 2);
            this.date = this.days[date.getDay()] + ' ' + this.addZero(date.getDate(), 2) + '-' + this.addZero(date.getMonth() + 1, 2) + '-' + this.addZero(date.getFullYear(), 4);
        },
        addZero(number, length) {
            var zero = '';
            for(var i = 0; i < length; i++) {
                zero += '0';
            }
            return (zero + number).slice(-length);
        }
    }
}
</script>

<style scoped>
p {
    padding: 0;
    margin: 0;
}
#clock {
    color: white;
    text-align: center;
    text-shadow: 0 0 20px rgba(10, 175, 230, 1),  0 0 20px rgba(10, 175, 230, 0);
}

.date {
    letter-spacing: 0.05em;
    font-size: 3vh;
}

.time {
    letter-spacing: 0.1em;
    font-size: 9vh;
}
</style>

