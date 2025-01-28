<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Job Application Portal</title>
    <link rel="stylesheet" href="styles.css">
    <script src="script.js" defer></script>
</head>
<body>
    <header>
        <div class="logo">
            <img src="pencil_logo.png" alt="Pencil Logo">
        </div>
        <nav>
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#services">Services</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home">
            <div class="profile">
                <img src="profile_picture.jpg" alt="Mr. Ajaharul Ahmed">
                <h1>Mr. Ajaharul Ahmed</h1>
                <h2>Interviewer</h2>
                <p>Explore premium job opportunities and business partnerships here.</p>
                <button class="apply-button" onclick="scrollToSection('services')">Apply for Job</button>
            </div>
        </section>

        <section id="services">
            <div class="service-card">
                <h3>Writing Job</h3>
                <p>Join our team of professional writers and contribute to high-quality content creation.</p>
                <button class="apply-now-button" onclick="openForm('Writing Job')">Apply Now</button>
            </div>
            <div class="service-card">
                <h3>Online Jobs</h3>
                <p>Explore various online job opportunities and work flexibly from anywhere.</p>
                <button class="apply-now-button" onclick="openForm('Online Jobs')">Apply Now</button>
            </div>
            <div class="service-card">
                <h3>Business Partnership</h3>
                <p>Collaborate with us for mutual business growth and success.</p>
                <button class="apply-now-button" onclick="openForm('Business Partnership')">Apply Now</button>
            </div>
        </section>

        <section id="contact">
            <h2>Contact Us</h2>
            <p>If you have any questions, feel free to send an email to: <a href="mailto:mrajaharulahned.business@gmail.com">mrajaharulahned.business@gmail.com</a></p>
        </section>
    </main>

    <footer>
        <p>Full Form Job. All Rights Reserved. Designed by Mr. Ajaharul Ahmed.</p>
    </footer>

    <div id="application-form-modal" class="modal">
        <div class="modal-content">
            <span class="close-button" onclick="closeForm()">&times;</span>
            <h2 id="form-title">Apply for Job</h2>
            <form id="application-form" onsubmit="submitForm(event)">
                <input type="hidden" id="job-type" name="jobType">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>
                <label for="dob">Date of Birth:</label>
                <input type="date" id="dob" name="dob" required>
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
                <label for="state">State:</label>
                <input type="text" id="state" name="state" required>
                <label for="city">City:</label>
                <input type="text" id="city" name="city" required>
                <label for="comments">Comments:</label>
                <textarea id="comments" name="comments"></textarea>
                <label for="photo">Photo Upload:</label>
                <input type="file" id="photo" name="photo" required>
                <button type="submit" class="submit-button">Submit</button>
            </form>
        </div>
    </div>
</body>
</html>
body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: #121212;
    color: #ffffff;
}

header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px 20px;
    background-color: #1c1c1c;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
}

.logo img {
    height: 40px;
}

nav ul {
    list-style: none;
    display: flex;
    gap: 20px;
}

nav ul li {
    display: inline;
}

nav ul li a {
    text-decoration: none;
    color: #ffffff;
}

main {
    padding: 20px;
}

#home {
    text-align: center;
    padding: 50px 0;
}

.profile img {
    border-radius: 50%;
    width: 150px;
    height: 150px;
}

.apply-button {
    background-color: #000000;
    color: #ffffff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    cursor: pointer;
    transition: transform 0.3s ease;
}

.apply-button:hover {
    transform: scale(1.05);
}

#services {
    display: flex;
    justify-content: space-around;
    padding: 20px 0;
}

.service-card {
    background-color: #1c1c1c;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    width: 30%;
    text-align: center;
}

.apply-now-button {
    background-color: #000000;
    color: #ffffff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    cursor: pointer;
    transition: transform 0.3s ease;
}

.apply-now-button:hover {
    transform: scale(1.05);
}

footer {
    background-color: #1c1c1c;
    text-align: center;
    padding: 10px 0;
    box-shadow: 0 -2px 4px rgba(0, 0, 0, 0.5);
}

.modal {
    display: none;
    position: fixed;
    z-index: 1000;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.5);
}

.modal-content {
    background-color: #1c1c1c;
    margin: 10% auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
    max-width: 500px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
}

.close-button {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
    cursor: pointer;
}

.close-button:hover,
.close-button:focus {
    color: #fff;
}

input, textarea {
    width: 100%;
    padding: 10px;
    margin: 5px 0;
    background-color: #2c2c2c;
    color: #ffffff;
    border: none;
    border-radius: 5px;
}

.submit-button {
    background-color: #000000;
    color: #ffffff;
    padding: 10px 20px;
    border: none;
    border-radius: 5px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
    cursor: pointer;
    transition: transform 0.3s ease;
}

.submit-button:hover {
    transform: scale(1.05);
}

@media (max-width: 768px) {
    #services {
        flex-direction: column;
        align-items: center;
    }

    .service-card {
        width: 80%;
        margin-bottom: 20px;
    }
}function scrollToSection(sectionId) {
    document.getElementById(sectionId).scrollIntoView({ behavior: 'smooth' });
}

function openForm(jobType) {
    document.getElementById('application-form-modal').style.display = 'block';
    document.getElementById('job-type').value = jobType;
    document.getElementById('form-title').innerText = `Apply for ${jobType}`;
}

function closeForm() {
    document.getElementById('application-form-modal').style.display = 'none';
}

function submitForm(event) {
    event.preventDefault();
    // Collect form data
    const formData = new FormData(document.getElementById('application-form'));

    // Simulate form submission
    alert('Form Submitted Successfully');

    // Clear form data
    document.getElementById('application-form').reset();
    closeForm();

    // TODO: Implement email sending functionality
}