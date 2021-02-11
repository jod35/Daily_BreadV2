<template>
  <section class="main">
    <div class="left" id="left">
      <div class="form">
        <form class="add" v-on:submit="saveVerse">
          <fieldset>
            <h3>Add Your Record</h3>
          </fieldset>
          <fieldset>
            <label for="verse">Verse</label>
            <input type="text" v-model="verse" />
          </fieldset>
          <fieldset>
            <label for="notes"> Notes </label>
            <textarea rows="5" cols="30" v-model="notes"></textarea>
          </fieldset>
          <fieldset>
            <button type="submit" class="btn mybtn">Save</button>
          </fieldset>
        </form>
      </div>
    </div>
    <div class="right">
      <div class="verses">
        <div class="verse" v-for="v in verses" v-bind:key="v.id">
          <small class="verse-id">Verse ID: {{ v.id }}</small>
          <h3 class="verse-name">{{ v.verse }}</h3>
          <p class="verse-notes">{{ v.notes }}</p>
          <div class="options">
            <a href="#" class="del-btn"
              ><i
                class="fa fa-trash"
                aria-hidden="true"
                v-on:click="deleteVerse(v.id)"
                >Delete</i
              ></a
            >
            <a href="#" class="update-btn"><i class="fa fa-feather">Edit</i></a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  name: "Main",
  components: {},
  data() {
    return {
      verse: "",
      notes: "",
      count: 1,
      verses: [],
    };
  },
  methods: {
    saveVerse() {
      this.verses.unshift({
        id: this.count,
        verse: this.verse,
        notes: this.notes,
      });
      console.log(this.verses);
      this.count++;
    },
    deleteVerse(verseId) {
      // let verse = this.verses.find((verse) => verse.id == verseId);

       this.verses.splice(verseId,1)
    },
  },
};
</script>

<style scoped>
.main {
  position: relative;
  top: 70px;
  display: flex;
  justify-content: space-between;
}
.left {
  width: 25%;
  color: black;
  min-height: 100vh;
}
.form {
  position: fixed;
  margin-top: 20px;
}

fieldset {
  border: none;
  padding: 10px;
}
textarea,
input {
  width: 90%;
  padding: 10px;
  border-radius: 7px;
  border: 0.9px solid black;
}

.btn {
  padding: 20px;
  border: none;
  text-transform: uppercase;
  border-radius: 10px;
  cursor: pointer;
  transition: all 1.2s;
  width: 90%;
}
.mybtn {
  padding: 20px;
  color: white;
  background-color: dodgerblue;
  border: none;
  border-radius: 7px;
  cursor: pointer;
}
.right {
  /* background-color: rgb(8, 13, 17); */
  width: 70%;
}
.verses {
  padding: 5% 0, 0, 0;
  margin-top: 5%;
}
.verses > .verse + .verse {
  margin-top: 20px;
}
.verse {
  width: 80%;
  padding: 20px;
  margin: auto;

  background-color: white;
  transition: all 1.2s;
}
.verse:hover {
  margin-left: 5px;
}
.options {
  padding: 10px;
}
.options a {
  font-size: 25px;
}
.options > a + a {
  margin: 20px;
}
.del-btn {
  color: red;
}
.update-btn {
  color: rgb(39, 161, 39);
}
</style>