<script>
    import github_img from '$lib/images/github.png'
    import linkedin_img from '$lib/images/linkedin.png'
    import email_img from '$lib/images/email.png'
</script>

<div class="splash-container">
    <div class="splash">
        <h1 class="splash-header">WILLIAM GOODSON</h1>
        <p class="splash-subheader">ASPIRING BACK-END WEB DEVELOPER</p>
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



    .splash h1, p, ul {
        width: 100%;
    }

    .splash h1 {
        margin: 5px 0;
        font-size: 48px;
    }

    .splash li {
        margin: 10px 5px    ;
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