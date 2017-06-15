<template>
	<div>
		<input 
			type="text"
			:placeholder="placeholder"
	        @keyup='up'
		/>
		 <ul 
          slot="result"
          class="typeahead"
        >
        	<li v-if="results.length == 0">No result foud</li>
            <li v-else v-for="result in results">
            	<a :href="'/link/' + result.id">
            		{{ result[displayKey] }}
            	</a>
        	</li>
        </ul>
	</div>
</template>
<script>
	export default {
		props: {
			placeholder: {
				Type: 'String',
				Default: 'Tyeahead Search'
			},
			displayKey: {
				Type: 'String',
				Required: true
			}
		},
		data () {
			return {
				items: [
					{
						id: 1,
						name: 'Anjo Tadena'
					},{
						id: 2,
						name: 'Ranie Pabualan'
					},{
						id: 3,
						name: 'Johnny Ramos'
					},{
						id: 4,
						name: 'Apple Joe Pacomios'
					},{
						id: 5,
						name: 'Eric Bray Quita'
					},{
						id: 6,
						name: 'John Mark Liwat'
					},{
						id: 7,
						name: 'Junivie Gorgonio'
					},
			     ],
			     results: []
			};
		},
		methods: {
			up (e) {
				this.results = [];
				this.results = this.items.filter((item) => {
					return item.name.indexOf(e.target.value) >= 0
				})
			}
		}
	}
</script>
