<template>
    <div class="best-students-block">
        <h2 class="best-students-block_title">{{title}}</h2>
        <div class="best-students-block_item"
             v-for="(student, i) in students"
             :key="i">{{student}}</div>
    </div>
</template>

<script>
import './best-students.scss';
export default {
    props: ['title', 'students']
}
</script>