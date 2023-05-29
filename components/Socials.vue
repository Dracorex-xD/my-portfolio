<template lang="en">
    <div class="socials-container">
        <div class="social" id="socialOne"><a href="https://github.com/Dracorex-xD"><img src="../assets/github.png" alt="GITHUB"></a></div>
        <div class="social" id="socialTwo"><a href="https://www.instagram.com/_zacharias_lee_/"><img src="../assets/instagram.png" alt="INSTAGRAM"></a></div>
        <div class="social" id="socialThree"><img src="../assets/discord.png" alt="DISCORD" @click="copyText('917317984618426399')"></div>
        <div class="social" id="socialFour"><img src="../assets/mail.png" alt="EMAIL" @click="copyText('zackaryleebusyness@gmail.com')"></div>
        <div class="social" id="socialFive"><img src="../assets/Phone.png" alt="PHONE" @click="copyText('0493542992')"></div>
    </div>
</template>
<script>
export default {
    name: 'Socials',
    methods: {
        copyText(string) {
            navigator.clipboard.writeText(string);
            alert(`Copied to clipboard: ${string}`);
        }
    }

}
</script>
<style scoped>
.socials-container {
    overflow: hidden;
    width: 100%;
    display: flex;
    height: 20rem;

}

#socialOne {
    animation: animate 20s infinite alternate-reverse linear;
}

#socialTwo {
    animation: animate 20s 1s infinite alternate-reverse linear;
}

#socialThree {
    animation: animate 20s 2s infinite alternate-reverse linear;
}

#socialFour {
    animation: animate 20s 3s infinite alternate-reverse linear;
}

#socialFive {
    animation: animate 20s 4s infinite alternate-reverse linear;
}

.social {
    position: relative;
    border-radius: 50%;
    width: 100px;
    height: 100px;
}

@keyframes animate {
    15% {
        top: 83%;
        left: 45%;

    }

    30% {
        top: 40%;
        left: 90%;

    }

    45% {
        top: 0%;
        left: 50%;

    }

    60% {
        top: 60%;
        left: 0%;

    }

    75% {
        top: 82%;
        left: 30%;

    }

    90% {
        top: 40%;
        left: 82%;


    }

    100% {
        top: 0;
        left: 0;
    }
}
</style>