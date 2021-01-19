<template>
    <div class="contact-wrapper">
            <div class="contact_left">
                <h1 class="title">Contact Us</h1>
                <p class="subhead">We’re Here to Help</p>
                <p class="content">Have questions about our internet marketing service?
                    Let’s talk about how can we help you achieve your goals
                    And take your business to the top!</p>
            </div>
            <div class="contact_right">
                <form class="rulesForm" @submit.prevent="submitForm">
                    <label for="name">
                        <p>Name</p>
                        <input type="text" autocomplete="off" v-model="name" class="inp" id="name">
                    </label>
                    <label for="email">
                        <p>Email</p>
                        <input type="text" autocomplete="off" v-model="email" class="inp" id="email">
                    </label>
                    <label>
                        <p>Message</p>
                        <textarea @input="handleChange" cols="30" rows="8" class="content talk"></textarea>
                    </label>
                    <button class="btn">SUBMIT</button>
                </form>
            </div>
        </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            email: '',
            content: ''
        }
    },
    methods: {
        handleChange(e) {
            this.content = e.target.value;
        },
        validate() {
            const reg = /^([a-zA-Z]|[0-9])(\w|\-)+@[a-zA-Z0-9]+\.([a-zA-Z]{2,4})$/;
            if (this.name == '' || this.name.trim().length == 0) {
                window.alert('Please fill in your name!');
                return false;
            } else if (this.email == '' || !reg.test(this.email)) {
                window.alert('Please fill in your email account!');
                return false;
            } else if (this.content == '' || this.content.trim().length == 0) {
                window.alert('Please fill in the content!');
                return false;
            }

            return true;
        },
        submitForm() {
            const flag = this.validate();

            if (flag) {
                new Promise((resolve,reject) => {
                    let t = setTimeout(() => {
                        window.alert('Submitted successfully!')
                        resolve();
                        this.resetForm();
                        clearTimeout(t);
                    },2000)
                })
            }
        },
        resetForm() {
            this.name = '';
            this.email = '';
            this.content = '';
        }
    }
}
</script>

<style lang="scss" scoped>
@import '~/assets/scss/contact.scss';
</style> 
