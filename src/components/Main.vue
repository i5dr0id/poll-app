<template>
  <div class="container">
	<div class="row">
		<div class="col-md-12">
			<h1>{{ title }}</h1>
			<h3 style="color:"> {{ desc }} </h3>
		</div>
	</div>
	<div class="row poll-box">
		<form class="container">
			<div class="form-group">
				<p>Enter your question here: </p>
				<textarea  style="font-family:'Josefin Slab', serif" placeholder="Question"></textarea>
			</div>

			<div class="form-group">
				<p>Add your options here: </p>
				<div class="poll-options">
					<input autocompelete="off" type="text" style="font-family:'Josefin Slab', serif" placeholder="Option 1">
				</div>
			</div>

			<div class="">
				<button type="submit" class="btn btn-default" style="font-family:'Josefin Slab', serif">Create Poll</button>
			</div>
		</form>
	</div>
  </div>
</template>

<script>
export default {
  name: 'Main',
  data() {
    return {
	  title: 'Poll App',
	  desc: 'Create a poll'
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main-container {
	text-align: center;
}
h1 {
	font-family: 'Josefin Slab', serif;
	font-weight: bold;
 
}

h3 {
	margin-top: 50px;
	font-family: 'Josefin Slab', serif;
	font-weight: 100;
}

.poll-box {
	margin-top: 20px;
}
form > div > p {
	font-family: 'Josefin Slab', serif;
	font-size: 1.17em;
}
textarea {
	height: 180px;
	width: 50%;
	border: none;
	border-radius: 8px;
	color: #4E4868;
	font-size: 26px;
	font-weight: 500;
	line-height: 30px;
	outline: none;
	padding: 24px 16px;
	resize: none;
	text-align: center;
}

input[type=text] {
	border: 0;
	box-sizing: border-box;
	width: 20%;
	max-width: 20%;
	border-radius: 7px;
	border: none;
	padding: 8px 16px;
	outline: none;
	text-align: center;
	margin-bottom: 10px;
	line-height: 36px;
	font-size: 18px;

}

button {
	box-sizing: border-box;
	margin: 0;
	width: 20%;
	background-color: #4E4868;
	border-radius: 8px;
	color : #ffffff;
	/* display: inline-block; */
	font-size: 20px;
	font-weight: 500;
	padding: 24px;
	text-align: center;
	text-decoration: none;
}
</style>
