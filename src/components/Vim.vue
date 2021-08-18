<template>
    <div class="vim padded">
        <br/>
        <p v-for="(line, i) in lines" :key="i">
            <span style="color:yellow">{{`${i + 1} `}} </span> 
            <span v-if="line.comment" class="cyan">{{`${comment} `}} </span>
            <span :class="{ cyan: line.comment }">{{line.content}}</span>
        </p>
        <br/>
    </div>
</template>

<script scoped>
export default {
name: 'Vim',
    props: {
        lines: Array,
        comment: String
    }
}
</script>

<style>

.cyan {
    color: cyan;
}
.vim {
    font-family: monospace;
    background: black;
    color: lightgray;
    font-size: 15px;
    line-height: 130%;
    width: max-content;
}

.padded {
    padding: 0 2em 0 2em;
}
</style>
