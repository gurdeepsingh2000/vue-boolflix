<template>
    <div class="navbar">
        <img src="https://assets.brand.microsites.netflix.io/assets/493f5bba-81a4-11e9-bf79-066b49664af6_cm_1440w.png?v=8" alt="">
        <div class="list-menu">
            <ul>
                <li>Home</li>
                <li>Serie Tv</li>
                <li>Film</li>
                <li>Originali</li>
                <li>Aggiunti di recente</li>
                <li>La mia Lista</li>
            </ul> 
        </div>

        <div class="user-options">
            <input placeholder="Inserisci il nome di un fim" type="text" v-model="userinput"  @keyup.enter="$emit('search',userinput)">
            <span>BAMBINI</span>
            <div><i class="fas fa-bell"></i></div>
            <img src="https://ih1.redbubble.net/image.618427277.3222/flat,800x800,075,f.u2.jpg" alt="">
        </div>

    </div>
</template>

<script>
    export default {
        name:'Header',
        data() {
            return{
                userinput: ''
            } 
        }
    }
</script>

<style lang="scss" scoped>

    .navbar{
        display: flex;
        background-color: black;
        height: auto;
        width: 100%;
        align-items:center ;

        img{
            width: 160px;
            height: 80px;
        }

        .list-menu{
            flex-grow: 1;
            ul{
                display: flex;
                list-style: none;

                li{
                    margin-right: 10px;
                    color:white

                };
            }
        }


        .fa-bell{
                font-size:30px;
                color: #fff;
            }
        
        .user-options{
            display: flex;
            align-items: center;
            width: 25%;
            justify-content: space-evenly;
            margin: 0 20px;


            img{
                width: 40px;
                height: 40px;
                background-color: grey;
            }

            img:nth-child(3){
                width: 30px;
                height: 30px;
                }

            span{
                color: white;
                font-size: 20px;
            }
        }
    }
    
</style>