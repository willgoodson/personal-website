<script lang="ts">
    import github_img from '$lib/images/github.png'
    import linkedin_img from '$lib/images/linkedin.png'
    import email_img from '$lib/images/email.png'
    import { onMount } from 'svelte'

    // TYPING ANIMATION
    const texts = [
        {text: "BACK-END WEB DEVELOPER", color: "coral"},
        {text: "SITE RELIABILITY ENGINEER", color: "green"},
        {text: "DATABASE ADMINISTRATOR", color: "purple"},
    ]

    let typed_text = "";
    let typed_color = "";

    async function type_sentence(sentence:String, delay = 80) {
        const letters = sentence.split("");
        let i = 0;
        for (let i = 0; i < letters.length; i++) {
            await wait(delay);
            typed_text += letters[i];
        }
        return;
    }

    async function delete_sentence() {
        let length = typed_text.length
        while (length != 0) {
            typed_text = typed_text.slice(0, -1)
            length = typed_text.length
            await wait(100)
        }

    }

    function wait(ms:number) {
        return new Promise(resolve => setTimeout(resolve, ms))
    }

    onMount(async ()=> {
        let text_selector = 0;
        while (true) {
            typed_color = texts[text_selector].color
            await type_sentence(texts[text_selector].text)
            await wait(800)
            await delete_sentence()
            await wait(400)
            text_selector++;
            if (text_selector > texts.length -1) {
                text_selector = 0;
            }
        }

    })

</script>

<div class="splash-container">
    <div class="splash">
        <h1 class="splash-header">WILLIAM GOODSON</h1>
        <div class="splash-subheader">
            <span id="static-words">ASPIRING&nbsp;</span>
            <span style="color: {typed_color}" id="typed-words">{typed_text}</span>
            <span class="input-cursor"></span>
        </div>
        <ul class="splash-links pure-menu pure-menu-horizontal pure-menu-list">
            <li class="splash-link pure-menu-item">
                <a href="https://github.com/willgoodson/"><img src={github_img} alt="Github" width="50px"></a>
            </li>
            <li class="splash-link pure-menu-item">
                <a href="https://www.linkedin.com/in/goodsonwill/"><img src={linkedin_img} alt="LinkedIn" width="50px"></a>
            </li>
            <li class="splash-link pure-menu-item">
                <a href="mailto:contact@williamgoodson.com"><img src={email_img} alt="Resume" width="50px"></a>
            </li>
        </ul>
    </div>
    <footer>
        <p>&copy William Goodson</p>
    </footer>
</div>

<style>
    * {
        margin: 0;
        padding: 0;
        font-family: 'Poppins', sans-serif;
    }
    .splash-container {
        height: 100vh;
        width: 100vw;
        display: grid;
        place-items: center;
    }

    .splash-container footer{
        position: absolute;
        bottom: 10px;
    }

    .splash {
        display: flex;
        flex-wrap: wrap;
        width: 50vw;
        text-align: center;
    }



    .splash h1, div, ul {
        width: 100%;
    }

    .splash h1 {
        margin: 5px 0;
        font-size: 48px;
    }

    .splash li {
        margin: 10px 5px    ;
    }

    .splash-subheader {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .input-cursor {
        display: inline-block;
        width: 2px;
        height: 18px;
        background-color: black;
        margin-left: 8px;
        animation: blink .6s linear infinite alternate;
    }

    @keyframes blink {
        0% {opacity: 1;}
        40% {opacity: 1;}
        60% {opacity: 0;}
        100% {opacity: 0;}
    }


/* Mobile Devices */
@media (max-device-width: 767px) {
    .splash {
        display: flex;
        flex-wrap: wrap;
        width: 100vw;
        text-align: center;
    }
}
</style>