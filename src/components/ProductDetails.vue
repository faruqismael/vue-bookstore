<template>
    <div class="container">
      <div class="row mt-4">
        <div class="col-sm-4">
          <img src="https://picsum.photos/350/300?image=1073"/>
        </div>
        <div class="col-sm-8">
          <h3>{{product.Title}}</h3>
          <hr>
          <p>Author: {{product.Author}}</p>
          <p>Publisher: {{product.Publisher}}</p>
          <p>Genre: {{product.Genre}}</p>
          <hr>
          <p>Price: ${{product.Price}}</p>
          <hr>
          <p>"Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur, vel illum qui dolorem eum fugiat quo voluptas nulla pariatur?"</p>
          <hr>
          <b-btn variant="primary" @click.prevent="updateCart(product)">Add to Cart</b-btn>
        </div>
      </div>
    </div>
</template>

<script>
import Data from '../assets/book_list.json'
export default {
  name: 'ProductDetails',
  props: ['updateCart'],
  data () {
    return {
      collection: Data.collection,
      product: []
    }
  },
  created () {
    this.product = this.collection.find((item) => {
      return item.Title === this.$route.params.productID
    })
  }
}
</script>

<style scoped>

</style>
