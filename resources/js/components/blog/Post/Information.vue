<template>
    <aside class="col-lg-4 agileits-w3ls-right-blog-con text-right">
        <div class="right-blog-info text-left">
            <div class="tech-btm">
                <img src="images/banner1.jpg" class="img-fluid" alt="">
            </div>
            <div class="tech-btm">
                <h4>Sign up to our newsletter</h4>
                <p>Pellentesque dui, non felis. Maecenas male </p>
                <form action="#" method="post">
                    <input type="email" placeholder="Email" required="">
                    <input type="submit" value="Subscribe">
                </form>

            </div>

            <div class="tech-btm">
                <h4>Categories</h4>
                <ul class="list-group single">
                    <div  v-for="category in categories">
                        <category :title="category.title" :time="category.created_at" :id="category.id"></category>
                    </div>
                </ul>
            </div>

            <div class="tech-btm">
                <h4>Top stories of the week</h4>

                <div class="blog-grids row mb-3">
                    <div class="col-md-5 blog-grid-left">
                        <a href="single.html">
                            <img src="images/1.jpg" class="img-fluid" alt="">
                        </a>
                    </div>
                    <div class="col-md-7 blog-grid-right">

                        <h5>
                            <a href="single.html">Pellentesque dui, non felis. Maecenas male non felis </a>
                        </h5>
                        <div class="sub-meta">
										<span>
											<i class="far fa-clock"></i> 20 Jan, 2018</span>
                        </div>
                    </div>

                </div>
                <div class="blog-grids row mb-3">
                    <div class="col-md-5 blog-grid-left">
                        <a href="single.html">
                            <img src="images/6.jpg" class="img-fluid" alt="">
                        </a>
                    </div>
                    <div class="col-md-7 blog-grid-right">
                        <h5>
                            <a href="single.html">Pellentesque dui, non felis. Maecenas male non felis </a>
                        </h5>
                        <div class="sub-meta">
										<span>
											<i class="far fa-clock"></i> 20 Feb, 2018</span>
                        </div>
                    </div>

                </div>
            </div>
            <div class="single-gd my-5 tech-btm">
                <h4>Our Progress</h4>
                <div class="progress">
                    <div class="progress-bar progress-bar-striped" role="progressbar" style="width: 10%" aria-valuenow="10" aria-valuemin="0"
                         aria-valuemax="100"></div>
                </div>
                <div class="progress">
                    <div class="progress-bar progress-bar-striped bg-success" role="progressbar" style="width: 25%" aria-valuenow="25" aria-valuemin="0"
                         aria-valuemax="100"></div>
                </div>
                <div class="progress">
                    <div class="progress-bar progress-bar-striped bg-info" role="progressbar" style="width: 50%" aria-valuenow="50" aria-valuemin="0"
                         aria-valuemax="100"></div>
                </div>
                <div class="progress">
                    <div class="progress-bar progress-bar-striped bg-warning" role="progressbar" style="width: 75%" aria-valuenow="75" aria-valuemin="0"
                         aria-valuemax="100"></div>
                </div>
                <div class="progress">
                    <div class="progress-bar progress-bar-striped bg-danger" role="progressbar" style="width: 100%" aria-valuenow="100" aria-valuemin="0"
                         aria-valuemax="100"></div>
                </div>
            </div>
            <div class="single-gd tech-btm">
                <h4>Recent Post</h4>
                <div class="blog-grids">
                    <div class="blog-grid-left">
                        <a href="single.html">
                            <img src="images/b1.jpg" class="img-fluid" alt="">
                        </a>
                    </div>
                    <div class="blog-grid-right">

                        <h5>
                            <a href="single.html">Pellentesque dui, non felis. Maecenas male</a>
                        </h5>
                    </div>
                    <div class="clearfix"> </div>
                </div>
            </div>
        </div>

    </aside>
</template>

<script>
import Category from "./Information/Category";

export default {
    name: "Information",
    components: {
        Category,
    },
    data: () => ({
        categories: []
    }),
    mounted() {
        this.loadCategories()
    },
    methods: {
        loadCategories()
        {
            axios.get('/api/categories')
                .then(res => {
                    this.categories = res.data
                })
        }
    }
}
</script>

<style scoped>

</style>
