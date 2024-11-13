<script>
    import { onMount } from 'svelte';

    const scriptURL = 'https://script.google.com/macros/s/AKfycbwxX72UNgWKfih_w4j_dCYNK2gsuXxP79Ms7U5RIe-KdDucd3S-fisUvdn78ZBV5FC0CQ/exec';
    let form, dialogOverlay, loadingBox, successBox, submitButton, textarea, emailInput, nameInput, msgSpan;

    // List of allowed email domains
    const allowedDomains = ["gmail.com", "yahoo.com", "outlook.com", "hotmail.com", "protonmail.com"];

    const handleSubmit = async (e) => {
        e.preventDefault();  // Prevent the default form submission

        // Check if name is valid
        const name = nameInput.value.trim();
        if (name.length < 2) {
            msgSpan.textContent = "Please enter a valid Name.";
            msgSpan.style.color = "red";
            setTimeout(() => (msgSpan.textContent = ""), 3000);
            return;
        }

        // Basic email format check
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        if (!emailRegex.test(emailInput.value)) {
            msgSpan.textContent = "Please enter a valid email address.";
            msgSpan.style.color = "red";
            setTimeout(() => (msgSpan.textContent = ""), 3000);
            return;
        }

        // Extract domain and check against allowed domains
        const emailDomain = emailInput.value.split("@")[1].toLowerCase();
        if (!allowedDomains.includes(emailDomain)) {
            msgSpan.textContent = `Please enter an email address with a valid domain (e.g., ${allowedDomains.join(", ")}).`;
            msgSpan.style.color = "red";
            setTimeout(() => (msgSpan.textContent = ""), 3000);
            return;
        }

        // Message length validation (minimum 10, maximum 500 characters)
        const message = textarea.value.trim();
        if (message.length < 5) {
            msgSpan.textContent = "Message must be 5 minimum characters.";
            msgSpan.style.color = "red";
            setTimeout(() => (msgSpan.textContent = ""), 3000);
            return;
        }
        if (message.length > 500) {
            msgSpan.textContent = "Maximum of 500 characters only.";
            msgSpan.style.color = "red";
            setTimeout(() => (msgSpan.textContent = ""), 3000);
            return;
        }

        // If validation passes, proceed with sending the message
        showLoadingBox();
        submitButton.disabled = true;

        try {
            await fetch(scriptURL, { method: 'POST', body: new FormData(form) });
            hideLoadingBox();
            showSuccessBox();
            form.reset();
        } catch (error) {
            console.error('Error!', error.message);
        } finally {
            submitButton.disabled = false;
            msgSpan.textContent = ""; // Clear error message if any
        }
    };

    function showLoadingBox() {
        loadingBox.style.display = 'flex';
    }

    function hideLoadingBox() {
        loadingBox.style.display = 'none';
    }

    function showSuccessBox() {
        successBox.style.display = 'flex';
        setTimeout(() => {
            successBox.style.display = 'none';
        }, 5000);
    }
</script>

<section class="contact" id="contact">
    <div class="content-container">
        <div class="contact-left">
            <h1 class="contact-heading">Get in Touch</h1>
            <i class="fa-solid fa-paper-plane"></i><a href="#" target="_blank" class="gmail_anchor"> pyschie313@gmail.com</a>
            <p><i class="fa-solid fa-phone"></i>  0994 559 1883</p>
            <div class="social-icons">
                <a href="https://www.facebook.com/jymce.bertillo/" target="_blank"><i class="fa-brands fa-facebook"></i></a>
                <a href="https://x.com/JBCB32446518" target="_blank"><i class="fa-brands fa-square-x-twitter"></i></a>
                <a href="https://www.instagram.com/jymceeee/?hl=en" target="_blank"><i class="fa-brands fa-instagram"></i></a>
            </div>
        </div>
        <div class="contact-right">
            <form bind:this={form} name="submit-to-google-sheet" on:submit={handleSubmit}>
                <input bind:this={nameInput} type="text" name="Name" placeholder="Your Name" required style="resize: none; width: 100%;">
                <input bind:this={emailInput} type="email" name="Email" placeholder="Your Email" required style="resize: none; width: 100%;">
                <textarea bind:this={textarea} name="Message" rows="6" placeholder="Your Message" style="resize: none;"></textarea>
                <div class="submit-button-container">
                    <button bind:this={submitButton} type="submit" class="btn btn-submit">Send Message</button>
                </div>
                <div class="submit-container"><span bind:this={msgSpan} id="msg"></span></div>
            </form>
        </div>
        
    </div>

    <!-- Loading and Success Boxes -->
    <div bind:this={loadingBox} class="message-box" id="loading-box">
        <p>Sending...</p>
    </div>
    <div bind:this={successBox} class="message-box" id="success-box">
        <p>Message Sent!</p>
    </div>
</section>

<style>
    /* Layout */
    .contact {
        padding: 40px;
        background-color: #c3b091;
        color: #ECDFCC;
        text-align: center;
    }

    .content-container {
        display: flex;
        max-width: 900px;
        background-color: #af855c;
        padding: 2rem;
        border-radius: 8px;
        gap: 2rem;
        margin: 0 auto;
        color: #ECDFCC;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Add box shadow */
    }

    .contact-heading {
        font-size: 3rem;
        margin-bottom: 15px;
    }

    .contact-left {
        flex: 1;
        padding-right: 2rem;
        text-align: left;
    }

    .gmail_anchor {
        margin: 0.5rem 0;
        color: #ECDFCC;
        font-size: 0.96rem;
        padding-bottom: 100px;
    }

    .fa-solid {
        padding-right: 1px;
    }

    .contact-left p {
        padding-top: 20px;
        padding-bottom: 20px;
        font-size: 1rem;
        font-size: 0.96rem;
    }
    .social-icons{
        padding-top: 5px;
    }
    .social-icons a {
        color: #ECDFCC;
        font-size: 1.8rem;
        margin-right: 1rem;
        transition: color 0.3s, transform 0.3s;
    }

    .social-icons a:hover {
        color: #B22222;
        transform: scale(1.1);
    }

    .btn-download {
        display: inline-block;
        margin-top: 1.5rem;
        padding: 0.8rem 1.5rem;
        background-color: #697565;
        color: #1E201E;
        text-decoration: none;
        border-radius: 4px;
        transition: background-color 0.3s;
        font-size: 1.1rem;
    }

    .btn-download:hover {
        background-color: #3C3D37;
    }

    .contact-right {
        flex: 1;
    }

    form {
        display: flex;
        flex-direction: column;
    }

    form input, form textarea {
        margin-bottom: 1rem;
        padding: 1rem;
        border: 1px solid #697565;
        border-radius: 4px;
        font-size: 1.1rem;
        color: #1E201E;
    }

    form input:focus, form textarea:focus {
        border-color: #ECDFCC;
    }

    .submit-container {
        padding-top: 25px;
        font-size: 1rem;
        color: #ECDFCC;
    }

    .submit-button-container {
    display: flex;
    justify-content: center; /* Center the button horizontally */
    margin-top: 1rem; /* Add some spacing above the button if needed */
    }

    .btn-submit {
        padding: 1rem 2rem;
        background-color: #8c6b59;
        color: #1E201E;
        border: none;
        border-radius: 4px;
        font-size: 1.2rem;
        cursor: pointer;
        transition: background-color 0.3s;
        max-width: 250px;
    }

    .btn-submit:hover {
        background-color: #c3b091;
    }

    /* Message Boxes for Loading and Success */
    .message-box {
        display: none;
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        padding: 20px;
        background-color: #e7decc;
        color: #262626;
        border-radius: 8px;
        font-size: 1.4rem;
        z-index: 1000;
        justify-content: center;
        width: 300px;
        opacity: 80%;
    }
    .fa-solid.fa-paper-plane{
        padding-right: 5px;
    }
    /* Media Query for Mobile (650px and below) */
    @media (max-width: 650px) {
        .content-container {
            flex-direction: column;
            padding: 1.5rem;
            gap: 1rem;
        }

        .contact-heading {
            font-size: 2.5rem;
        }

        .contact-left, .contact-right {
            padding: 0;
            text-align: center;
        }

        .contact-right{
            padding-top: 30px;
        }

        .contact-left p {
            font-size: 1rem;
        }

        .social-icons a {
            font-size: 1.5rem;
            margin-right: 0.5rem;
        }

        .btn-download {
            padding: 0.6rem 1.2rem;
            font-size: 1rem;
        }

        form input, form textarea {
            font-size: 1rem;
            padding: 0.8rem;
        }

        .btn-submit {
            padding: 0.8rem 1.5rem;
            font-size: 1.1rem;
        }

        .message-box {
            width: 250px;
            font-size: 1.2rem;
        }
    }
</style>