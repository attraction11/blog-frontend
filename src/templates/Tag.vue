<template>
        <Layout>
        <!-- Page Header -->
        <header class="masthead" style="background-image: url('/img/home-bg.jpg')">
            <div class="overlay"></div>
            <div class="container">
                <div class="row">
                    <div class="col-lg-8 col-md-10 mx-auto">
                        <div class="site-heading">
                            <h1>{{ $page.tag.title }}</h1>
                        </div>
                    </div>
                </div>
            </div>
        </header>

        <!-- Main Content -->
        <div class="container">
            <div class="row">
                <div class="col-lg-8 col-md-10 mx-auto">
                    <div class="post-preview" v-for="post in $page.tag.posts" :key="post.id">
                        <g-link :to="'/post/'+ post.id">
                            <h2 class="post-title">
                                {{ post.title }}
                            </h2>
                            <!-- <h3 class="post-subtitle">
                                Problems look mighty small from 150 miles up
                            </h3> -->
                        </g-link>

                    </div>

                    <!-- Pager -->
                    <!-- <div class="clearfix">
                        <a class="btn btn-primary float-right" href="#">Older Posts &rarr;</a>
                    </div> -->
                </div>
            </div>
        </div>
    </Layout>
</template>

<page-query>
query ($id: ID) {
	tag: strapiTag (id: $id) {
        id
        title
        posts {
            id
            title
        }
    }
}
</page-query>

<script>
export default {
    name: 'TagPage',
    data() {
        return {}
    },
    created() {},
    mounted() {},
    methods: {},
}
</script>

<style scoped lang="scss"></style>
