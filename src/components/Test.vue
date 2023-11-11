<template>
  <div id='test'>
    <h1>Multi-form tests</h1>
    <div v-for='(loopData, index) in loopTest' :class='{ hidden: true, active: formPosition === index + 1 }' :key='index'>
      {{ loopData.name }}
      <input type='text' :placeholder='loopData.placeholder' />
    </div>
    <div>
      <button @click='previous'>Previous</button>
      <button @click='next'>Next</button>
      <button>Submit</button>
    </div>
  </div>
</template>

<script>
  export default {
    data: () => {
      return {
        formPosition: 1,
        loopTest: [{
          name: 'Title 1',
          placeholder: 'Name'
        }, {
          name: 'Title 2',
          placeholder: 'Age'
        }, {
          name: 'Title 3',
          placeholder: 'Address'
        }]
      }
    },
    methods: {
      next() {
        if (this.formPosition < this.loopTest.length) {
          this.formPosition += 1
        }
      },
      previous() {
        if (this.formPosition > 1) {
          this.formPosition -= 1
        }
      }
    }
  }
</script>

