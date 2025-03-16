# matchmak3r
## credits
Eric Porgue Matchmaker-Lite, needed a lot of help for the calculations step as well, had a very hard time finding solutions.

<script> 

console.log("Starting System");

function calculateCompatibility () {
	console.log("Compatibility Calculations")

	const DESIRED_RESPONSE = [
		5, /* Greatly Agree */
		4, /* Agree   */
		3, /* Neutral */
		2, /* Disagree*/
		1, /* Greatly Disagree*/

	]

	let QResponse1 = document.Id("Q1").selectedOption[0].value;
	let QResponse2 = document.Id("Q2").selectedOption[0].value;
	let QResponse3 = document.Id("Q3").selectedOption[0].value;
	let QResponse4 = document.Id("Q4").selectedOption[0].value;
	let QResponse5 = document.Id("Q5").selectedOption[0].value;

	console.log("Q1 Responses:")
	console.log(document.getElementById("1").selectedOptions[0].text);
	console.log(document.getElementById("1").selectedOptions[0].value);
	console.log(QResponse1);

	console.log("Q2 Responses:")
	console.log(document.getElementById("2").selectedOptions[0].text);
	console.log(document.getElementById("2").selectedOptions[0].value);
	console.log(QResponse2);

	console.log("Q3 Responses:")
	console.log(document.getElementById("3").selectedOptions[0].text);
	console.log(document.getElementById("3").selectedOptions[0].value);
	console.log(QResponse3);

	console.log("Q4 Responses:")
	console.log(document.getElementById("4").selectedOptions[0].text);
	console.log(document.getElementById("4").selectedOptions[0].value);
	console.log(QResponse4);

	console.log("Q5 Responses:")
	console.log(document.getElementById("5").selectedOptions[0].text);
	console.log(document.getElementById("5").selectedOptions[0].value);
	console.log(QResponse5);

	let Q1Compatibility = 5 - Math.abs(Q1 - DESIRED_RESPONSE[1]);
	let Q2Compatibility = 5 - Math.abs(Q2 - DESIRED_RESPONSE[4]);
	let Q3Compatibility = 5 - Math.abs(Q3 - DESIRED_RESPONSE[3]);
	let Q4Compatibility = 5 - Math.abs(Q4 - DESIRED_RESPONSE[3]);
	let Q5Compatibility = 5 - Math.abs(Q5 - DESIRED_RESPONSE[4]);

	console.log("c1="+question1Compatibility);
	console.log("c2="+question2Compatibility);
	console.log("c3="+question3Compatibility);

	let Total = Q1Compatibility + Q2Compatibility + Q3Compatibility + Q4Compatibility + Q5Compatibility

	Total *= 100 / MaxScore;
	Total = Math.round(total);
	console.log ("final Compatibility" + Total);

	document.Id("compatibility").innerHTML = "You are"  + Total;

}


</body>
</script>
</html>

<p>Instructions:</p>
  <p>Answer the given questions and hit button to check your compatibility</p>
  <br /> <br />

  <label>I would join a cult for 100k a year </label><br />
	<select id="q1">
		<option value="5">Strongly Agree</option>
		<option value="4">Agree</option>
		<option value="3">Neither agree nor disagree</option>
		<option value="2">Disagree</option>
		<option value="1">Strongly Disagree</option>
	</select>
	<br /><br />
  
	<br />
  <label>Technogoly was more Innovative in the 90's than in the Present</label><br />
	<select id="q2">
		<option value="5">Strongly Agree</option>
		<option value="4">Agree</option>
		<option value="3">Neither agree nor disagree</option>
		<option value="2">Disagree</option>
		<option value="1">Strongly Disagree</option>
	</select>
	<br /><br />

	<br />
	<label>I am Interested In The Deep/Dark Web</label><br />
	<select id="q3">
		<option value="5">Strongly Agree</option>
		<option value="4">Agree</option>
		<option value="3">Neither agree nor disagree</option>
		<option value="2">Disagree</option>
		<option value="1">Strongly Disagree</option>
	</select>
	<br /><br />

	<br />
	<label>Weezer is the Greatest Band of all time</label><br />
	<select id="q4">
		<option value="5">Strongly Agree</option>
		<option value="4">Agree</option>
		<option value="3">Neither agree nor disagree</option>
		<option value="2">Disagree</option>
		<option value="1">Strongly Disagree</option>
	</select>
	<br /><br />
	
	<br />
	<label>Jurassic Park 2 is A Good Movie/Sequel</label><br />
	<select id="q5">
		<option value="5">Strongly Agree</option>
		<option value="4">Agree</option>
		<option value="3">Neither agree nor disagree</option>
		<option value="2">Disagree</option>
		<option value="1">Strongly Disagree</option>
	</select>
	<br /><br />

	<br />
	<button onclick="Compatibility()"> Your Compatibility is...</button>
	<p id="Your compatibility"></p>

	<script>
		console.log("Starting Matchmaker Lite...");
		
		function calculateCompatibility() {
			console.log("calculateCompatibility()");
		
			const DESIRED_RESPONSE = [
				5, /* strongly agree */
				2, /* disagree */
				1, /* strongly disagree */
			]
		
			const MAX_SCORE = 15;
		
			// Get the current values of the dropdown controls.
			let question1Response = document.getElementById("q1").selectedOptions[0].value;
			let question2Response = document.getElementById("q2").selectedOptions[0].value;
			let question3Response = document.getElementById("q3").selectedOptions[0].value;
			let question4Response = document.getElementById("q4").selectedOptions[0].value;
			let question5Response = document.getElementById("q5").selectedOptions[0].value;
		
			// Optionally log the values associated with question 1 through 3 to the console. 
			console.log("Question 1 Answers:")
			console.log(document.getElementById("q1").selectedOptions[0].text);
			console.log(document.getElementById("q1").selectedOptions[0].value);
			console.log(question1Response);
		
			console.log("Question 2 Answers:");
			console.log(document.getElementById("q2").selectedOptions[0].text);
			console.log(document.getElementById("q2").selectedOptions[0].value);
			console.log(question2Response);
		
			console.log("Question 3 Answers:");
			console.log(document.getElementById("q3").selectedOptions[0].text);
			console.log(document.getElementById("q3").selectedOptions[0].value);
			console.log(question2Response);
		
			// Todo: Calculate compatibility scores.
			let question1Compatibility = 5 - Math.abs(question1Response - DESIRED_RESPONSE[0]);
			let question2Compatibility = 5 - Math.abs(question2Response - DESIRED_RESPONSE[1]);
			let question3Compatibility = 5 - Math.abs(question3Response - DESIRED_RESPONSE[2]);
		
			console.log("c1="+question1Compatibility);
			console.log("c2="+question2Compatibility);
			console.log("c3="+question3Compatibility);
		
			// Calculate total compatibility. 
			let totalCompatibility = question1Compatibility + question2Compatibility + question3Compatibility;
		
			// Convert totalCompatibility to a percentage.
			totalCompatibility *= 100 / MAX_SCORE;
			totalCompatibility = Math.round(totalCompatibility);
			console.log("tc="+ totalCompatibility);
		
			document.getElementById("compatibility").innerHTML = "Your compatibility is: " + totalCompatibility;
		}

