<template>
  <div class="container">
    {{title}}
    <div class="form">
      <div class="form-group">
        <div class="form-group">
          <label>Comment Title</label>
          <input class="form-control" type="text" v-model="comment.title" />
        </div>
        <div class="form-group">
          <label>Comment Title</label>
          <textarea class="form-control" type="text" v-model="comment.text"></textarea>
        </div>
      </div>
      <button class="btn btn-primary" @click="addComments">Submit</button>
    </div>

    <div class="col-sm-12">
      <div class="col-sm-4" v-for="(comment, index) in comments" v-bind:key="comment.title">
        <div class="card">
          <button class="close" @click="removeComment(index)" name="button">&times;</button>
          <div class="card-block">
            <h4 class="card-title">{{comment.title}}</h4>
            <h6 class="card-subtitle mb-2 text-muted">{{comment.date}}</h6>
            <p class="card-text">{{comment.text}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>



<script>
export default {
  name: "Comments",
  data() {
    return {
      title: "Leave your comments",
      comment: {
        title: "",
        text: ""
      },
      comments: [
        {
          title: "Loveee this machine",
          text: "Better car street",
          date: new Date(Date.now()).toLocaleString()
        }
      ]
    };
  },
  methods: {
    addComments() {
      let { title, text } = this.comment;

      this.comments.push({
        text,
        title,
        date: new Date(Date.now()).toLocaleString()
      });

      this.comment.title = "";
      this.comment.text = "";
    },
    removeComment(index) {
      this.comments.splice(index, 1);
    }
  }
};
</script>
