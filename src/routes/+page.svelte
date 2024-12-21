<script>
	let currentDate = new Date().toLocaleDateString();
</script>

<div class="wrapper">
	<div class="container">
		<h1>Site Under Construction</h1>
		<p>We're working on something special. Please check back soon.</p>
		<p class="date">Current Date: {currentDate}</p>
		</div>
</div>


<style>
.wrapper {
	margin: 0;
	font-family: 'Helvetica Neue', Arial, sans-serif;
	background-color: #dae0b9;
	background-size: cover;

	color: #ffffff;
	text-align: center;
	display: flex;
	justify-content: center;
	align-items: center;
	height: 100vh;
	overflow: hidden;
}

.container {
	background: rgba(100, 100, 100, 0.5);
	padding: 2rem;
	border-radius: 15px;
	max-width: 500px;
	width: 90%;
}

h1 {
	margin: 0;
	line-height: 1.2;
}

p {
	margin: 1rem 0 0;
	line-height: 1.5;
}

.date {
	margin-top: 1rem;
	opacity: 0.8;
}
</style>
