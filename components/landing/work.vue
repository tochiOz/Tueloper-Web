<template>
  <div id="Projects">
    <div class="project-text">
      <span class="what animated slideInUp">Some Things I've Built</span>
      <div class="d-flex align-items-center">
        <p class="get text-center">Projects</p>
        <hr />
      </div>
    </div>
    <div class="card-columns">
      <CardP v-for="project of projects" :key="project.id" :project="project" />
    </div>
  </div>
</template>

<script>
import CardP from './../card'

export default {
  components: {
    CardP
  },
  data() {
    return {
      // cards: cards,
      // newFront: '',
      // newBack: '',
      // error: false,
      projects: [
        {
          id: 1,
          title: 'My journey with Vue',
          content: 'This is where i learnt some crazy things'
          // stacks: [Firebase]
        },
        {
          id: 2,
          title: 'Blogging with Vue',
          content: 'This is where i learnt some crazy things'
          // stacks: [Vue, Firebase]
        },
        {
          id: 3,
          title: 'Why Vue is so fun',
          content: 'This is where i learnt some crazy things'
          // stacks: [Vue, Firebase]
        }
      ]
    }
  },
  methods: {
    toggleCard: function(card) {
      card.flipped = !card.flipped
    },
    addNew: function() {
      if (!this.newFront || !this.newBack) {
        this.error = true
      } else {
        this.cards.push({
          front: this.newFront,
          back: this.newBack,
          flipped: false
        })
        // set the field empty
        this.newFront = ''
        this.newBack = ''
        // Make the warning go away
        this.error = false
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.card {
  font-family: 'Poppins';
  height: 25rem;
  border-radius: 0 !important;
}
.head {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
#Projects {
  height: auto;
  padding: 100px 0;
  font-family: 'Poppins';
}

body {
  font-family: 'Montserrat', sans-serif;
  text-align: center;
}

ul {
  padding-left: 0;
  display: flex;
  flex-flow: row wrap;
}

li {
  list-style-type: none;
  padding: 10px 10px;
  transition: all 0.3s ease;
}

.container {
  max-width: 100%;
  padding: 2em;
}

// .card {
//   display: block;
//   width: 150px;
//   height: 175px;
//   padding: 80px 50px;
//   background-color: #51aae5;
//   border-radius: 7px;
//   margin: 5px;
//   text-align: center;
//   line-height: 27px;
//   cursor: pointer;
//   position: relative;
//   color: #fff;
//   font-weight: 600;
//   font-size: 20px;
//   -webkit-box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
//   -moz-box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
//   box-shadow: 9px 10px 22px -8px rgba(209, 193, 209, 0.5);
//   will-change: transform;
// }

li:hover {
  transform: scale(1.1);
}

li:nth-child(-n + 3) .card {
  background-color: #e65f51;
}

li:nth-child(2n + 1) .card {
  background-color: #a17de9;
}

li:nth-child(4n) .card {
  background-color: #feca34;
}

li:nth-child(5n-2) .card {
  background-color: #51aae5;
}

li:nth-child(4n + 4) .card {
  background-color: #feca34;
}

li:nth-child(-7n + 7) .card {
  background-color: #e46055;
}

.delete-card {
  position: absolute;
  right: 0;
  top: 0;
  padding: 10px 15px;
  opacity: 0.4;
  transition: all 0.5s ease;
}

.delete-card:hover,
.error {
  opacity: 1;
  transform: rotate(360deg);
}

.flip-enter-active {
  transition: all 0.4s ease;
}

.flip-leave-active {
  display: none;
}

.flip-enter,
.flip-leave {
  transform: rotateY(180deg);
  opacity: 0;
}

/* Form */
.flashcard-form {
  position: relative;
}

label {
  font-weight: 400;
  color: #333;
  margin-right: 10px;
}

input {
  border-radius: 5px;
  border: 2px solid #eaeaea;
  padding: 10px;
  outline: none;
}

button {
  border-radius: 5px;
  border: 1px solid #87cb84;
  background-color: #87cb84;
  padding: 8px 15px;
  outline: none;
  font-size: 14px;
  font-weight: 700;
  color: #fff;
  cursor: pointer;
  transition: all 0.3s ease;
}

button:hover {
  background-color: #70a66f;
}

.error {
  margin-top: 10px;
  display: block;
  color: #e44e42;
  font-weight: 600;
}
</style>
