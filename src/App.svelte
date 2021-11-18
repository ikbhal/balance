<script>
class Section {
	constructor(name, color, sections=[]){
		this.name = name;
		this.color = color;
		this.sections = sections;
	}
}
let sections = [
	new Section("spirituality", "#aaa", ["Iman", "Namaz", "Ramzaan", "Zakat", "Haz"]),
	new Section("health","#bbb", ["toilet", "drink water", "healthy food", "bath", "exercise"]),
	new Section("family", "#ccc", ["parents", "wife", "kids", "friends", "relatives"]),
	new Section("work", "#ddd", ["Job", "business", "investment"]),
	new Section("society", "#eee", ["sadkah", "teach kids", "youtube video"])
];
</script>

<main>
	<h2>Balance</h2>
	<p>Balance spirituality, health, family, career, society</p>


	<div class="row">
		{#each sections as section}
			<div class="column" style="background-color:{section.color};">
				<h2>{section.name}</h2>
				<ul>
					{#each section.sections as sec}
					<li>{sec}</li>
					{/each}
				</ul>
			</div>
		{/each}
	</div>
</main>

<style>
* {
  box-sizing: border-box;
}

/* Create four equal columns that floats next to each other */
.column {
  float: left;
  width: 20%;
  padding: 10px;
  height: 300px; /* Should be removed. Only for demonstration */
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}
</style>