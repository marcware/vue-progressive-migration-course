<template>  
  <div>
    <h3 class="mb-4">Comments</h3>

    <comments-item 
      v-for="comment in orderedComments" 
      :key="comment.id"
      :username="comment.username"
      :avatar="comment.avatar"
      :date="comment.date"
      :comment="comment.comment"
    ></comments-item>

  </div>
</template>


<script>
import _ from 'lodash'

import CommentsItem from './CommentsItem'

export default {
  props: ['comments'],
  components: { CommentsItem },
   computed: {
    orderedComments: function () {
      return _.orderBy(this.comments, 'date', 'desc')
    }
  },
}
</script>