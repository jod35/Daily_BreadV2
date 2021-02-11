<template>
    <header>
		<div class="nav-bar">
			<a href="#" class="nav-bar-open" id="open-nav">&#9776;</a>
			<a href="#" class="nav-bar-close" onclick="closeModal('left')">&times;</a>
		</div>
		<div class="logo"><h3>Daily Bread</h3></div>
		<div>
			<button class="clear">Clear</button>
		</div>
		<div class="count-cont">
			
		</div>
	</header>
</template>

<script>
export default {
    name:"NavBar"
}
</script>
<style >
header{
           padding: 18px;
            width: 100%;
            position: fixed;
            top: 0;
            display: flex;
            justify-content: space-between;
            color: #fff;
            background-color: dodgerblue;
            z-index: 1;
}
.nav-bar{
	display: none;
}
.nav-bar a{
	color: white;
	font-size: 2em;
	text-decoration: none;
}
.nav-bar-close{
	display: none;
}

.clear{
	padding: 10px;
	border: none;
	text-transform: uppercase;
	border-radius: 10px;
	background-color:;
	color: blue;
	font-weight: bold;
	transition: all 1.2s;
	cursor: pointer;
	display: none;
}
.clear:hover,.btn:hover{
	color: white;
	background: blue;
}
.count-cont{
	padding-top: 10px;
	font-size: 1.2em;
	font-weight: bold;
}
</style>