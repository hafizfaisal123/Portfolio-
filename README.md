<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Abdullah Portfolio</title>
	<link rel="stylesheet" href="style.css">
</head>
<body>
	<!-- Hero Section -->
	<section class="hero">
	<h1>Muhammad Faisal</h1>
	<p>Frontend Developer</p>
	<a href="#contact" class="btn">Contact Me</a>
	</section>

	<!-- Tech Stack Section -->
	<section id="tech-stack" class="tech-stack">
		<h2>Tech Stack</h2>
		<div class="tech-icons">
			<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5" title="HTML5">
			<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3" title="CSS3">
			<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" title="JavaScript">
			<!-- Add more icons as needed -->
		</div>
	</section>

	<!-- Projects Section -->
	<section id="projects" class="projects">
		<h2 style="font-size:2.5rem;color:#38ef7d;text-align:center;margin-bottom:32px;letter-spacing:2px;">Featured Projects</h2>
		<div class="project-list" style="display:flex;flex-wrap:wrap;gap:32px;justify-content:center;">
			<div class="project" style="background:#232526;padding:28px;border-radius:14px;width:320px;box-shadow:0 2px 12px #11998e44;">
				<h3 style="color:#38ef7d;">Simple Calculator</h3>
				<p>A modern calculator app with instant results.</p>
				<button class="btn" onclick="openModal('calculator')">Run Demo</button>
			</div>
			<div class="project" style="background:#232526;padding:28px;border-radius:14px;width:320px;box-shadow:0 2px 12px #11998e44;">
				<h3 style="color:#38ef7d;">Image Gallery</h3>
				<p>Responsive gallery with stylish hover effects.</p>
				<button class="btn" onclick="openModal('gallery')">Run Demo</button>
			</div>
			<div class="project" style="background:#232526;padding:28px;border-radius:14px;width:320px;box-shadow:0 2px 12px #11998e44;">
				<h3 style="color:#38ef7d;">Contact Form</h3>
				<p>Animated contact form with validation.</p>
				<button class="btn" onclick="openModal('contact')">Run Demo</button>
			</div>
			<div class="project" style="background:#232526;padding:28px;border-radius:14px;width:320px;box-shadow:0 2px 12px #11998e44;">
				<h3 style="color:#38ef7d;">To-Do List</h3>
				<p>Manage your daily tasks with a simple to-do app.</p>
				<button class="btn" onclick="openModal('todo')">Run Demo</button>
			</div>
			<div class="project" style="background:#232526;padding:28px;border-radius:14px;width:320px;box-shadow:0 2px 12px #11998e44;">
				<h3 style="color:#38ef7d;">Weather App</h3>
				<p>Check the weather instantly for any city.</p>
				<button class="btn" onclick="openModal('weather')">Run Demo</button>
			</div>
		</div>

<!-- Modals for project demos -->
<div id="modal-bg" style="display:none;position:fixed;top:0;left:0;width:100vw;height:100vh;background:rgba(35,37,38,0.85);z-index:1000;justify-content:center;align-items:center;">
	<div id="modal-content" style="background:#232526;padding:32px 24px;border-radius:16px;max-width:400px;width:90vw;box-shadow:0 2px 16px #11998e44;position:relative;">
		<button onclick="closeModal()" style="position:absolute;top:12px;right:16px;background:#38ef7d;color:#232526;border:none;border-radius:50%;width:32px;height:32px;font-size:1.2rem;cursor:pointer;">&times;</button>
		<div id="modal-inner"></div>
	</div>
</div>

<script>
function openModal(type) {
	document.getElementById('modal-bg').style.display = 'flex';
	let inner = '';
	if(type === 'calculator') {
		inner = `<h3 style='color:#38ef7d;'>Simple Calculator</h3>
			<input type='number' id='num1' placeholder='Num 1' style='width:60px;text-align:center;'>
			<select id='op'>
				<option value='+'>+</option>
				<option value='-'>-</option>
				<option value='*'>*</option>
				<option value='/'>/</option>
			</select>
			<input type='number' id='num2' placeholder='Num 2' style='width:60px;text-align:center;'>
			<button onclick='calcRun()' style='margin-top:10px;' class='btn'>Calculate</button>
			<div id='calc-result' style='margin-top:10px;'></div>`;
	} else if(type === 'gallery') {
		inner = `<h3 style='color:#38ef7d;'>Image Gallery</h3>
			<img src='images.jpg' alt='Gallery Image 1' style='width:120px;height:80px;object-fit:cover;margin:8px;border-radius:8px;box-shadow:0 2px 8px #11998e44;'>
			<img src='images (1).jpg' alt='Gallery Image 2' style='width:120px;height:80px;object-fit:cover;margin:8px;border-radius:8px;box-shadow:0 2px 8px #11998e44;'>
			<img src='download.jpg' alt='Gallery Image 3' style='width:120px;height:80px;object-fit:cover;margin:8px;border-radius:8px;box-shadow:0 2px 8px #11998e44;'>`;
	} else if(type === 'contact') {
		inner = `<h3 style='color:#38ef7d;'>Contact Form</h3>
			<form onsubmit='sendForm(event)'>
				<input type='text' placeholder='Your Name' required>
				<input type='email' placeholder='Your Email' required>
				<textarea placeholder='Your Message' required></textarea>
				<button type='submit' class='btn'>Send</button>
			</form>`;
	} else if(type === 'todo') {
		inner = `<h3 style='color:#38ef7d;'>To-Do List</h3>
			<input type='text' id='todo-input' placeholder='Add a task...' style='width:70%;padding:8px;'>
			<button onclick='addTodo()' class='btn' style='margin-top:8px;'>Add</button>
			<ul id='todo-list' style='margin-top:16px;padding-left:0;'></ul>`;
	} else if(type === 'weather') {
		inner = `<h3 style='color:#38ef7d;'>Weather App</h3>
			<input type='text' id='weather-city' placeholder='Enter city...' style='width:70%;padding:8px;'>
			<button onclick='getWeather()' class='btn' style='margin-top:8px;'>Check</button>
			<div id='weather-result' style='margin-top:16px;'></div>`;
	}
	document.getElementById('modal-inner').innerHTML = inner;
}
function closeModal() {
	document.getElementById('modal-bg').style.display = 'none';
}
function calcRun() {
	var a = parseFloat(document.getElementById('num1').value);
	var b = parseFloat(document.getElementById('num2').value);
	var op = document.getElementById('op').value;
	var result;
	if (op === '+') result = a + b;
	else if (op === '-') result = a - b;
	else if (op === '*') result = a * b;
	else if (op === '/') result = b !== 0 ? a / b : 'Error';
	else result = 'Invalid';
	document.getElementById('calc-result').textContent = 'Result: ' + result;
}
function sendForm(e) {
	e.preventDefault();
	alert('Message sent!');
}
function addTodo() {
	var input = document.getElementById('todo-input');
	var val = input.value.trim();
	if(val) {
		var ul = document.getElementById('todo-list');
		var li = document.createElement('li');
		li.textContent = val;
		li.style.listStyle = 'none';
		li.style.background = '#2c5364';
		li.style.color = '#38ef7d';
		li.style.padding = '8px';
		li.style.marginBottom = '6px';
		li.style.borderRadius = '6px';
		ul.appendChild(li);
		input.value = '';
	}
}
function getWeather() {
	var city = document.getElementById('weather-city').value.trim();
	if(city) {
		document.getElementById('weather-result').textContent = 'Weather in ' + city + ': Sunny, 28°C';
	}
}
</script>
		</div>
	</section>

	<!-- About Section -->
	<section id="about" class="about">
		<h2>About Me</h2>
		<p>I am a passionate frontend developer with experience in modern web technologies.</p>
	</section>

	<!-- Contact Section -->
	<section id="contact" class="contact">
		<h2>Contact</h2>
		<p>WhatsApp: <a href="https://wa.me/923136991739" target="_blank">0313-6991739</a></p>
		<form>
			<input type="text" placeholder="Your Name" required>
			<input type="email" placeholder="Your Email" required>
			<textarea placeholder="Your Message" required></textarea>
			<button type="submit">Send</button>
		</form>
	</section>
</body>
</html># Portfolio-
Personal portfolio.
