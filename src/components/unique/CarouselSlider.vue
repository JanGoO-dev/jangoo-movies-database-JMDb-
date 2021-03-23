<template>

    <div v-show="lengthOfImagesArray <= 10" class="container mt-5 text-center">

        <div class="spinner-border m-5" role="status">
            
            <span class="visually-hidden">Loading...</span>

        </div>

    </div>

    <div v-show="lengthOfImagesArray > 0" id="carouselSlider" class="container mt-5 carousel carousel-light slide" data-bs-ride="carousel">

        <div class="carousel-indicators">

            <button 
                v-for="(s, index) in trendingMovies" 
                :key="index" type="button" 
                data-bs-target="#carouselSlider" 
                :data-bs-slide-to="index" 
                :aria-label="'Slide' + index"
                :class="{ active: index == 0 }"
                :aria-current="{ true: index == 0, false: index != 0 }"
            ></button>

        </div>
        
        <div class="carousel-inner shadow-lg rounded-lg">
        
            <div 
                v-for="(movie, index) in trendingMovies"
                :key="index"
                class="carousel-item"
                :class="{ active: index == 0 }"
                data-bs-interval="10000"
            >
                
                <!-- <img :src="'https://image.tmdb.org/t/p/original' + movie.movie_landscape_poster" class="d-block w-100"> -->
                <lazy-image
                    :width="3840"
                    :height="2160"
                    background-color="rgb(255, 107, 107)"
                    :lazy-src="'https://image.tmdb.org/t/p/original' + movie.movie_landscape_poster"
                />
                
                <div class="carousel-caption carousel-caption-position d-none d-md-block">
                
                    <div class="carousel-caption-bg pt-3 pb-2 ps-4 mb-3">
                        
                        <h5 class="display-6 ps-5">{{ movie.movie_title }}</h5>

                    </div>
                
                </div>
            
            </div>
        
        </div>
        
        <button class="carousel-control-prev" type="button" data-bs-target="#carouselSlider"  data-bs-slide="prev">
        
            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        
            <span class="visually-hidden">Previous</span>
        
        </button>
        
        <button class="carousel-control-next" type="button" data-bs-target="#carouselSlider"  data-bs-slide="next">
        
            <span class="carousel-control-next-icon" aria-hidden="true"></span>
        
            <span class="visually-hidden">Next</span>
        
        </button>
    
    </div>

</template>

<script>
import axios from "axios";
import LazyImage from "../global/LazyImage";

export default {
    name: "CarouselSlider",
    data() {
        return {
            trendingMovies: [],
        };
    },
    components: {
        LazyImage,
    },
    computed: {
        lengthOfImagesArray() {
            return this.trendingMovies.length;
        }
    },
    methods: {
        async getImage() {
            let i = 0;
            return await axios.get("https://api.themoviedb.org/3/trending/movie/day?api_key=91eb3c751fd1da1a7ef55b3795dcef20").then(response => {
                response.data.results.forEach(element => {
                    this.trendingMovies.push({
                        "id": element.id,
                        "index": i++,
                        "movie_title": element.title,
                        "movie_landscape_poster": element.backdrop_path
                    });
                });
                console.log(this.trendingMovies);
            });
        }
    },
    created() {
        this.getImage();
    }
}
</script>

<style scoped>
.rounded-lg {
    border-radius: 10px;
}

.carousel-caption-bg {
    background: #00000040;
    backdrop-filter: blur(3px);
}

.carousel-caption-position {
    position: absolute;
    left: 0;
    right: 0;
    text-align: left;
}
</style>