<template>
  <form class="d-flex">
      <div>
          <input 
          type="text" 
          class="form-control mt-3"
          placeholder="Cerca un personaggio"
          v-model.trim="searchText"
          @keyup="$emit('performSearch', searchText)"
          >
      </div>
      <div>
          <button
          type="submit"
          class="btn btn-primary form-control mt-3"
          @click.prevent="$emit('performSearch', searchText)"
          >
                Search
          </button>
      </div>
      <div>
          <button
          type="reset"
          class="btn btn-primary form-control mt-3"
          @click="resetSearch"
          >
                Reset
          </button>
      </div>
  </form>
</template>

<script>
export default {
    name: "Search",
    data: function() {
        return {
            searchText: ''
        }
    },
    computed: {
        uppercaseText: function() {
            return this.searchText.toUpperCase();
        }
    },
    methods: {
        resetSearch: function() {
            this.searchText = '';
            this.$emit('performSearch', this.searchText);
        }
    }
}
</script>

<style lang="scss" scoped>
    div {
        margin-right: 20px;
        
        input {
            background-color: #9dcb38;

            &:hover {
                background-color: #22b4cf;
            }
        }

        button {
            background-color: #9dcb38;

            &:hover {
                background-color: #22b4cf;
            }
        }
    }
</style>