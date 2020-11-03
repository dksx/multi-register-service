<template>
	<div class="notfound">
		<div class="notfound-404 grid-item">
			<h1>404</h1>
		</div>
		<div class="grid-item">
			<h2>PAGE NOT FOUND</h2>
		</div>
		<div class="grid-item">
			<p>The page you are looking for might have been removed,
         had its name changed or is temporarily unavailable.</p>
		</div>
		<div class="grid-item">
			<p><a href="/">Return to homepage</a></p>
		</div>
	</div>
</template>

<script>

export default {
  name: 'PageNotFound',
};
</script>

<style scoped>

h1 {
  font-size: 190px;
  font-weight: lighter;
  margin: 0px;
  background: linear-gradient(130deg, #ef5350, #d32f2f);
  color:transparent;
  -webkit-background-clip: text;
  background-clip: text;
  text-transform: uppercase;
}
</style>
