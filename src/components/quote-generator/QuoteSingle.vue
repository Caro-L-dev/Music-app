<script>
export default {
    props: ['quote']

}
</script>

<template>
    <section class="quote-single">
        <div class="quote-content">
            Content
        </div>
        <div class="quote-info">
            <div class="quote-title">Title</div>
            <div class="quote-author">Me</div>

        </div>
    </section>
</template>

<style scoped>
.quote-single {
    position: relative;
    margin: 0 auto;
    max-width: 72rem;
}

.quote-content {
    position: relative;
    font-size: 28px;
    font-weight: 600px;
    background-color: #131A26;
    color: white;
    padding: 6rem 3rem;
    border-radius: 1rem;
}

.quote-content:before,
.quote-content:after {
    content: '"';
    color: #848484;
    margin: 0rem 0.2rem;
}

.quote-info {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 1rem;
    color: white;
}

.quote-author,
.quote-title {
    position: absolute;
    padding: 1rem 2rem;
    font-size: 24px;
    font-weight: 700;
    border-radius: 0.5rem;
    text-align: center;
}

.quote-author {
    top: calc(100% - 3rem);
    right: 0;
    transform: translateY(-50%);
    transform: translateX(10%);
    background-color: #8A4FFF;
}

.quote-title {
    left: 0;
    background-color: #32CBFF;
    color: black;
    transform: translateX(-20%);
}
</style>