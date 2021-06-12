<template>
  <section class="characters container">
     <div class="row">

         <div class="col-12">
             <Search @performSearch="searchCharacter"/>
         </div>
        
        <!-- Array iniziale completo -->
        
         <!-- <div class="col-6 col-md-4 col-lg-3"
            v-for="character in characters"
            :key="character.id"
         >
             <Character 
             :item="character"
             />
         </div> -->

          <div class="col-6 col-md-4 col-lg-3"
            v-for="character in filteredCharacters"
            :key="character.id"
         >
             <Character 
             :item="character"
             />
         </div>

         <div class="col-12 mb-5">
             <ResultsMessage 
             :number="filteredCharacters.length"
             />
         </div>

     </div>
  </section>
</template>

<script>
import Character from './Character';
import Search from './Search';
import ResultsMessage from './ResultsMessage';
import axios from 'axios';

export default {
    name: "CharactersList",
    components: {
        Character,
        Search,
        ResultsMessage
    },
    data: function() {
        return {
            characters: [],
            searchFieldText: ''
        }
    },
    computed: {
        filteredCharacters: function() {

            if(this.characters == '') {
                return this.characters;
            }

            const newArray = this.characters.filter(
                (element) => {
                    // console.log(element);
                    return element.name
                    .toLowerCase()
                    .includes(
                        this.searchFieldText.toLowerCase()
                    );
                }
            );
            return newArray;
        }
    },
    methods: {
        searchCharacter: function(text) {
            // console.log("click sul pulsante");
            // console.log(text);
            this.searchFieldText = text;
        }
    },
    created: function() {
        axios
            .get('https://rickandmortyapi.com/api/character?page=5')
            .then(
                (response) => {
                    // console.log(response.data);
                    this.characters = response.data.results
                }
            )
            .catch();
    }
}
</script>

<style lang="scss" scoped>

</style>