<script>
	let isDiv2Hovered = false;

	function handleHover() {
		isDiv2Hovered = true;
	}

	function handleLeave() {
		isDiv2Hovered = false;
	}
</script>

{isDiv2Hovered}
<div id="div1">Div 1</div>
<div id="div2" on:mouseover={handleHover} on:mouseleave={handleLeave}>Div 2</div>

<style>
	/* Default styles for div1 and div2 */
	#div1 {
		background-color: blue;
		padding: 10px;
		color: white;
	}

	#div2 {
		background-color: red;
		padding: 10px;
		color: white;
	}
</style>
