<template>  
        <div class="uk-card-body">
            <h3 class="uk-card-title">dfdfdfd</h3>
        </div>
</template>

<script>  
    import itemsQuery from '../../apollo/queries/item/items'

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
            return item.age.toLowerCase().includes(this.query.toLowerCase())
          })
        },
      }
    }
</script>
