<template>
  <div class="hello">
    <h1> This is a child getting data from parent via injector.</h1>
    {{childMessage}}

    <p>Has register in course : {{ registerCourse }}</p>
  </div>
</template>

<script>

import {testMixin} from '../mixins/testMixin'

export default {
  name: 'ChildInjector',
  inject: ['childMessage'],
  mixins: [testMixin],
  data(){
    return {
      grade: 10,
      student: {
        name: 'John Doe',
        courses: [
          'DSA',
          'DBA',
          'SQA'
        ]
      }
    }
  },
  watch: {
    grade(newGrade, oldGrade) {
      console.log('old and new Grade', newGrade,  oldGrade)
    }
  },
  mounted() {
    this.grade = this.grade + 1
  },
  computed: {
    registerCourse() {
      return this.student.courses.includes('SQA')  ? 'Yes' : 'No'
    }
  }
  
}
</script>

<style>
</style>
