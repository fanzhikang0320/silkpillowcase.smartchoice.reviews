
<template>
    <div class="maskLayer">
        <div class="mask-content ">
            <span class="close"></span>
            <div class="mask-box clearfix">
                <div class="mask-left">
                    <img src="" alt="smart watch" class="ad">
                </div>
                <div class="mask-right">
                    <p class="offer">Limited Time Offer</p>
                    <p class="save"><span>SAVE</span><strong>50% MONEY</strong></p>
                    <p class="OEI">Offer Expires In</p>
                    
                    <div class="date-area">
                        <div class="time-box colon">
                            <span class="text">Hours</span>
                            <div class="time">
                                <span class="hours-decade">0</span>
                                <span class="hours-unit">0</span>
                            </div>
                        </div>
                        <div class="time-box colon">
                            <span class="text">Minutes</span>
                            <div class="time">
                                <span class="minutes-decade">0</span>
                                <span class="minutes-unit">0</span>
                            </div>
                        </div>
                        <div class="time-box">
                            <span class="text">Seconds</span>
                            <div class="time">
                                <span class="seconds-decade">0</span>
                                <span class="seconds-unit">0</span>
                            </div>
                        </div>
                    </div>
                    <p class="desc">30 Days Money Back Guarantee</p>
                    <a :href="mainLink" target="_blank" rel="noopener noreferrer" class="btn">Get the discount today!</a>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    
    data() {
        return {
            mainLink: 'https://www.emrldisle.com/88MJP83/3W3HD9N/?uid=2393&creative_id=11703',
            timer: null,
            timer1: null,
            count: 0
        }
    },
    methods: {
        
        countDown() {
            //结束时间
            let finishTime = new Date('2020/7/31').getTime();
            let startTime = new Date(new Date().toLocaleDateString()).getTime();
            let intervalTime = 0,
                day = 0,
                hours = 0,
                minutes = 0,
                seconds = 0;
            let that = this;
            this.timer = setInterval(function () {
                if (finishTime - new Date().getTime() <= 0) {
                     finishTime = new Date(new Date().toLocaleDateString()).getTime() + 1 * 24 * 60 * 60 * 1000;
                }
                intervalTime = finishTime - new Date().getTime();

                day =  Math.floor(intervalTime/(1000*60*60*24));
                hours = Math.floor(intervalTime / (60 * 60 * 1000) % 24) + day * 24;
                minutes = Math.floor(intervalTime / (60 * 1000) % 60);
                seconds = Math.floor(intervalTime / 1000 % 60); 
                that.renderTime(hours,minutes,seconds);
                
            },1000)
            
        },
        renderTime(hours,minutes,seconds) {
            let hoursObj = this.splitCell(hours);
            let minutesObj = this.splitCell(minutes);
            let secondsObj = this.splitCell(seconds);
            $('.hours-decade').text(hoursObj.decade);
            $('.hours-unit').text(hoursObj.unit);
            $('.minutes-decade').text(minutesObj.decade);
            $('.minutes-unit').text(minutesObj.unit);
            $('.seconds-decade').text(secondsObj.decade);
            $('.seconds-unit').text(secondsObj.unit);

        },
        splitCell(num) {
            let unit = Math.floor(num % 10);
            let decade = Math.floor(num / 10);
            return {
                unit: unit,
                decade: decade
            }
        },
        alert() {
            $('.maskLayer').css({
                display: 'block'
            })
            $('.mask-content').animate({opacity: 1,top: '50%'},400)
        },
        closeAlert() {
            $('.mask-content').animate({
                top: '40%',
                opacity: 0
            },400,function () {
                $('.maskLayer').css({
                    display: 'none'
                })
            })
            
            clearInterval(this.timer);
        }
    },
    mounted() {
        this.countDown();
        let that = this;
        this.timer1 = setTimeout(() => {
            $('body').on('mouseenter',function () {
                $('body').one('mouseleave',function () {
                    if (that.count == 0) {

                        that.alert();
                    }
                    that.count ++;
                })
            })
        },1000)
        
        $('.close').on('click',function (event) {
            event.stopPropagation();
            that.closeAlert();
        })
        $('.maskLayer').on('click',function (e) {
            e.stopPropagation();
            that.closeAlert();
        })
    },
    beforeDestroy() {

        $('body').off('mouseenter');
        clearInterval(this.timer);
        clearTimeout(this.timer1);
        this.timer = null;
    }
}
</script>

<style lang="scss" scoped>
@import './index.scss';
</style>
