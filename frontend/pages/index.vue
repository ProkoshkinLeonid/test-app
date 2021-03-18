<template>  
        <div>
          <div class="uk-card uk-card-default uk-grid-collapse uk-child-width-1-2@m uk-margin" v-for="item in filteredList" v-bind:key="item" uk-grid>
              <div>
                  <div class="uk-card-body">
                      <h3 class="uk-card-title">{{ item.age }}</h3>
                      <p>{{ item.id }}</p>
                  </div>
              </div>
          </div>

      </div>
</template>

<script>  
    import itemsQuery from '../apollo/queries/item/items'

    export default {  
      data() {
        return {
          items: [],
          query: ''
        }
      },
      apollo: {
        items: {
          prefetch: true,
          query: itemsQuery
        }
      },
      computed: {
        filteredList() {
          return this.items.filter(item => {
            return item.age
          })
        },
      }
    }
</script>