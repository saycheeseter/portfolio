<template>
    <div class="container--main">
        <div class="container--main__view">
            <router-view></router-view>
        </div>
        <div class="container--nav">
            <nav class="container--nav__center">
                <ul class="nav--column">
                    <li>
                        <router-link :to="{ name: 'home' }">Home</router-link>
                    </li>
                    <li class="pull-right">
                        <router-link :to="{ name: 'login' }">Login</router-link>
                    </li>                    
                    <!-- <li class="pull-right">
                        <router-link :to="{ name: 'register' }">Register</router-link>
                    </li> -->
                </ul>
            </nav>
        </div>
    </div>
</template>

<style lang="scss">
    body{
        margin:0;
        padding: 0;
    }
    .container--main{
        width: 100vw;
        display: flex;
    }
    .container--main__view{
        height: 100vh;
        flex: 1;
        background: rgb(235, 235, 235);
    }
    .container--nav{
        height: 100vh;
        .container--nav__center{
            height: 100%;
            display: flex;
            align-items: center;
            .nav--column{
                display: flex;
                list-style: none;
                flex-direction: column;
                justify-content: space-around;
                padding: 0;
                height: 50%;
                li{
                    transform: rotate(90deg);
                    list-style-type: none;
                    a{
                        height: 10px;
                        text-decoration: none;
                        color: rgb(62, 138, 237);
                        font-family: 'Anton', sans-serif;
                    }
                }
            }
        }
    }

    #scrollbar--dark::-webkit-scrollbar-track
    {
        -webkit-box-shadow: inset 0 0 6px rgba(0,0,0,0.3);
        background-color: #F5F5F5;
    }

    #scrollbar--dark::-webkit-scrollbar
    {
        width: 10px;
        background-color: #F5F5F5;
    }

    #scrollbar--dark::-webkit-scrollbar-thumb
    {
        background-color: #282828;
        border: 2px solid #3c3c3c;
    }

</style>
