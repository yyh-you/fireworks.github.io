<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>烟花秀</title>
		<link rel="stylesheet" href="firework.css">
	</head>
	<body>
		<div class="wrapper">
			<div class="wrapper-display">
				<p id="time">距离2022还有: 10时50分30秒</p>
				<br>
				<br>
				<br>
				<br>
				<br>
				<br>	<br>
				<br>
				<br>
				<p id="time">蔡诗怡新年快乐</p>
			</div>
			<span></span>
			<span></span>
		</div>
	
		<canvas id="canvas"></canvas>
	</body>
</html>
<script src="firework2.js"></script>
<script>
	
	let time = document.getElementById('time')
	
	
	function getTimeTo2022(){
		let curr = new Date()
		let hours = curr.getHours()
		let minutes = curr.getMinutes()
		let seconds = curr.getSeconds()
		
		let totsec = seconds + minutes * 60 + hours * 60 * 60
		
		totsec = 60 * 60 * 24 - totsec
		
		hours = Math.floor(totsec / 3600)
		minutes = Math.floor(totsec / 60 % 60)
		seconds = Math.floor(totsec % 60)
		
		console.log(hours,minutes,seconds)
		
		return `${hours}时${minutes}分${seconds}秒`
	}
	
	setInterval(refreshClock,1000)
	
	refreshClock()
	function refreshClock(){
		let date = new Date()
		let curr = date.getFullYear() * 10000 + date.getMonth() * 100 + date.getDate()
		let targ = 20250100
		// console.log(curr)
		if(curr < targ){
			time.innerText = '新年快乐！'
		}else{
			time.innerText = '距离2025年还有:' + getTimeTo2022()
		}
		time.innerText = '距离2025年还有:' + getTimeTo2022()
	}
</script>
