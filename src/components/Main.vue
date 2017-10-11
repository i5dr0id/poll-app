<template>
  <div class="container">
	<div class="row">
		<div class="col-md-12">
			<h1>{{ title }}</h1>
			<h3> {{ desc }} </h3>
		</div>
	</div>
	<div class="row poll-box">
		<form class="container">
			<div class="form-group">
				<p>Enter your question here: </p>
				<textarea></textarea>
			</div>

			<div class="form-group">
				<p>Add your options here: </p>
				<div v-show="p_options">
					<div v-for="(find, index) in finds" v-bind:key="index">
						<div class="poll-options">
							<input @keyup="addFind" :id="index" v-model="find.value" autocompelete="off" type="text" :placeholder="xyz">
						</div>
					</div>
				</div>
			</div>

			<div class="">
				<button type="submit" class="btn btn-default">Create Poll</button>
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
	  desc: 'Create a poll for your organization',
	  xyz: 'Option...',
	  p_options: ["Option 1"],
	  finds: [{text:""}] 
    };
  },
  methods: {
    addFind: function (e) {
    // console.log("id:", typeof e.target.id)
    // console.log("f lenght:", typeof this.finds.length - 1)
    if(e.target.id == this.finds.length - 1){
		e.target.isDirty = true;
      this.finds.push({ text: '' });
    }
	    if (e.target.isDirty && e.target.value == '') {
    	this.finds.splice(e.target.id, 1)
    }
  }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.main-container {
	text-align: center;
}
h1 {
	font-family: "Oswald", sans-serif;
	font-weight: bold;
 
}

h3 {
	margin-top: 50px;
	font-family: "Oswald", sans-serif;
	font-weight: 100;
	color: #7f8c8d;
}

.poll-box {
	margin-top: 20px;
}
form > div > p {
	font-family: "Oswald", sans-serif;
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

/* MEDIA QUERY */

@media only screen and (min-width: 320px) {
	/* Mobile Small: */
textarea {
	height: 180px;
	width: 100%;
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
	width: 50%;
	max-width: 50%;
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
	width: 100%;
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

}

@media only screen and (min-width: 375px) {
	/* Mobile medium: */

}

@media only screen and (min-width: 425px) {
	/* Mobile Large: */

}

@media only screen and (min-width: 768px) and (min-width: 900px){
	/* Tablet: */

}

@media only screen and (min-width: 1024px) {
	/* laptop */
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
}
</style>
