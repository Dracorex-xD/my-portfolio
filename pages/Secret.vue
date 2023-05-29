<template lang="en">
    <div class="container" @keypress="handleEnterKey">
        <div class="enter-password" v-if="!correctPassword">
            <input type="text" placeholder="Enter password..." ref="input">
            <button type="submit" @click="submit">Submit</button>
        </div>
        <div class="secret" v-if="correctPassword" ref="secret">
            <CallSidebar heading="I <3 Lyna Perez :)" />
        </div>
    </div>
</template>
<script>
export default {
    name: 'secret',
    data() {
        return {
            correctPassword: false,
            password: '123456' //your password should be hidden
        }
    },
    methods: {
        submit() {
            const input = this.$refs.input
            if (input.value === this.password) {
                this.correctPassword = true
            } else {
                alert('you somehow messed up the password')
            }
        },
        handleEnterKey(event) {
            if (event.key === 'Enter') {
                this.submit()
            }
        }
    }
}
</script>
<style></style>