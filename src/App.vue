<template>
  <div class="container-fluid">
    <article class="main-image">
        <section>
         <h1>Mohsen Portfolio</h1> 
         <span>A Free Bootsrap Template with Vue JS</span>
         <button class="btn btn-xl btn-light" @click="scrollTo('find-more')">Find Out More</button>  
        </section>
    </article>

   <article id="find-more" class="white-section">
    <section>
       <h3>Mohsen is C.I.S engineer , try to complete next step of projects </h3>
       <span>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</span>
       <button class="btn btn-xl btn-dark" @click="scrollTo('offers')">What We Offer</button>
    </section>
   </article> 
   <article id="offers" class="blue-section">
    <section class="container">
        <h2>What WE OFFer</h2>
        <div class="row">
          <div class="col-lg-3 col-md-6 mb-5 mb-lg-0" v-for="(offer,index) in offers " :key="index">
            <div class="icon mx-auto"><i class="fas" :class="offers.icon"></i></div>
            <h4>{{ offers.title }}</h4>
            <span>{{ offers.description }}</span>
          </div>  
        </div>
    </section>
   </article>
   <article class="second-image">
    <section>
        <h2>Welcome to <i>your</i><br>next website</h2>
        <button class="btn btn-xl btn-dark" @click="scrollTo('recent-projects')"> Recent Projects</button>
    </section>
   </article>
   <article id="recent-projects" class="white-section">
    <section class="container">
     <h3>Recent Projects</h3>
     <div class="row no-gutters">
        <div class="col-lg-6" v-for="(project , index) in recentProjects" :key="index">
          <a href="" class="protflio-item">
           <span class="caption">
            <span class="caption-content">
               <h2>{{ project.title }}</h2>
               <p class="mb-0">{{ project.description }}</p>
            </span>
           </span>
           <img class="img-fluid" src="require('../assets/'+ project.img)" alt="">
          </a>  
        </div>
     </div>
    </section>
   </article>
   <article>
    <section>
        <h2>Have nice day</h2>
        <button class="btn btn-xl btn-light mr-4" @click="scrollTo('app')">Click me </button>
        <button class="btn btn-xl btn-dark" @click="scrollTo('app')"> Look at me</button>
    </section>
   </article>
</div>
</template>

<script>
export default{
    data: () =>{
        return{
            offers: [
                {
                    icon: 'fa-mobile',
                    title: 'Responsive',
                    description:'Looks great on any screen size'
                },
                {
                    icon: 'fa-pencil-alt',
                    title: 'Redesigned',
                    description:'Freshly redesigned for Vue JS'
                },
                {
                    icon: 'fa-thumbs-up',
                    title: 'Favorited',
                    description:'Millions of users like us'
                },
                {
                    icon: 'fa-question-circle',
                    title: 'Questions?',
                    description:'We answer all questions'
                }
            ],
            recentProjects: [
                 {
                    img: 'C:\Users\AHMAD\Documents\modal-project\src\assets\gallery01.jpg',
                    title: 'Stationary',
                    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
                 },
                 {
                    img: 'C:\Users\AHMAD\Documents\modal-project\src\assets\gallery02.jpg',
                    title: 'Ice Cream',
                    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
                 },
                 {
                    img: 'C:\Users\AHMAD\Documents\modal-project\src\assets\gallery03.jpg',
                    title: 'Strawberries',
                    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
                 },
                 {
                    img: 'C:\Users\AHMAD\Documents\modal-project\src\assets\gallery04.jpg',
                    title: 'Workspace',
                    description: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.'
                 }
            ],
        }
    },

    methods: {
        scrollTo(element) {
            const el = document.querySelector('#'+element);
            el.scrollIntoView({
                behavior: 'smooth' ,
                block: 'start'
            });
        }
    }
}
</script>

<style lang="scss">
@import url('https://use.fontawsome.com/releases/v5.8.1/css/all.css');
@import url('https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css');

article{
display: flex;
justify-content: center;
align-items: center; 
width: 100%;
padding: 0 10px;
}
.btm-xl {
    padding: 20px 35px;
    font-family: serif;
    font-size: 1.25rem;
}

.main-image , .second-image{
    min-height: 100vh;
    background-size: cover;
    padding: 0 10px;
    text-align: center;
}

h1{
 font-size: 5rem;
 font-weight: bold;
}

h2{
 font-size: 5rem;
 font-weight: bold;
 margin-bottom: 30px;     
}

span {
    display: block;
    padding-bottom: 30px;
    font-size: 1.6rem;
    font-weight: bold;
}

.main-image{
    background: url('./assets/image-background.jpg')  ;
    background-position-x: left;
    background-size: 150%;
}
.white-section{
    padding: 120px 10px;
    background-color: #f5eaaa;
    text-align: center;

}

h3{
    font-size: 2rem;
    font-weight: bold;
}

span{
    display: block;
    padding-bottom: 30px;
    font-size: 1.25rem;
}
.row{
 padding-top: 50px;   
}

.portfolio-item{
    display: block;
    position: absolute;
    overflow: hidden;

    .caption{
        display: flex;
        height: 100%;
        width: 100%;
        position: absolute;
        top: 0;
        bottom: 0;
        z-index:1;
        background-color: rgba($color: #000000, $alpha: .2);
        transition: transform .2s linear;
        .caption-content{
            text-align: left;
            color: #faf7f7;
            margin: auto 2rem 2rem;
        }
        .img{
            transition: transform .2s linear;
        }
        &:hover{
            img{
                transform: scale(.9);
            }

            .caption{
                transform: scale(.9);
                background-color: rgba($color: #000000, $alpha: .5);
            }
        }
    }
}

.blue-section{
    padding: 120px 10px;
    background-color: #1d80;
    color: #fff;
    text-align: center;

    h2{
    font-size: 3rem;
    font-weight: bold;
    margin-bottom: 50px ;   
    }

    h4{
        font-size: 1.6rem;
        padding-top: 20px;
    }
    .icon{
        display: flex;
        justify-content: center;
        align-items: center;
        width: 120px;
        height: 120px;
        background-color: #fff;
        color: #1d809f;
        border-radius: 50%;

     i{
       font-size: 2rem; 
             }
    }
}
</style>
