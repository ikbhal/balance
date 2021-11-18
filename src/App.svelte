<script>
class Section {
	constructor(name, color, sections={compulsory:[]}){
		this.name = name;
		this.color = color;
		this.sections = sections;
	}
}

let priorityList = ["compulsory", 
"better",
"good"
];
let sections = [
	new Section("work", "#ddd", {
		compulsory:["Job", "business", "investment"],
		better: ["carreer growth", "business sales", "long term investment"],
		good: []
	}),
	new Section("family", "#ccc",{
		compulsory : ["parents", "wife", "kids", "friends", "relatives"],
		better: ["listen parents", "listen wife", "play with kids", "listen friends", "talk to relatives"],
		good: []
	}),
	new Section("spirituality", "#aaa", {
		compulsory: ["Iman", "Namaz", "Ramzaan", "Zakat", "Haz"],
		better: ["Quran", "Jikr", "Jamaat"],
		good: []
	}),
	new Section("health","#bbb", {
		compulsory:["toilet", "drink water", "healthy food", "bath", "exercise"],
		better: ["sleep early", "wakup early", "drink water morning", "bath alternate day", "walk daily"],
		good: []
	}),
	new Section("society", "#eee", {
		compulsory:["sadkah", "teach kids", "youtube video"],
		better: ["talk to neighbour", "surrounding street", "duwa for umma","partner with existing ngo"],
		good: []
	})
];
console.log("sections:", sections);
</script>

<main>
	<h2>Balance Life</h2>

	<div class="row">
		{#each sections as section}
			<div class="column" style="background-color:{section.color};">
				<h2>{section.name}</h2>
				<ul>
				{#each priorityList as priority}
					<li>
						<h3>{priority}</h3>
						{#each section.sections[priority] as sec}
							<p>{sec}</p>
						{/each}
					</li>
			
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
  height: 600px; /* Should be removed. Only for demonstration */
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}
</style>