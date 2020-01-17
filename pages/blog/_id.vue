<template>
    <div>
        <h1>Blog detail </h1>
        <p>{{ $route.params.id }}のエントリーです</p>
    </div>
</template>

<script>
export default {
    validate({ "params": params }) {
        return /^\d+$/.test(params.id)
    }
}
</script>