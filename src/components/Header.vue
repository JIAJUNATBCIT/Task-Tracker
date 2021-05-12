<template>
    <header>
        <h1>{{title}}</h1>
        <AppSwitch v-show="homePage"
        @toggle-add-task="$emit('toggle-add-task')" 
        :text="showAddTask ? 'Close': 'Add Task'" 
        :color="showAddTask ? 'red' : 'green'" />
    </header>
</template>

<script>
import AppSwitch from './AppSwitch'

export default {
    name: 'Header',
    props: {
        title: String,
        showAddTask: Boolean
    },
    components: {
        AppSwitch
    },
    computed: {
        homePage() {
            return this.$route.path === '/'
        }
    }
}
</script>

<style scoped>
    header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>
