<template>
    <div class="home-intro">
        <div class="home-intro__images"><slot name="images" /></div>
        <div class="home-intro__text"><slot /></div>
    </div>
</template>

<style>
    .home-intro{
        width: 85%;
        margin: auto;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        grid-gap: 30px;
        margin-top: 100px;
    }

    .home-intro__images{
        grid-column: 1 / 2;
    }

    .home-intro__images p img{
        max-width: 80%;
    }

    .home-intro__text{
        grid-column: 2 / 2;
    }

    .home-intro__text p {
        margin-top: 10px;
        font-family: 'Roboto';
        font-style: normal;
        font-weight: 300;
        font-size: 24px;
        line-height: 32px;
    }

    .home-intro__text h2{
        font-family: 'Roboto';
        font-style: normal;
        font-weight: 400;
        font-size: 50px;
        line-height: 59px;
        margin-top: 0;
    }

    .home-intro__text h2 a {
        text-decoration: none;
        color: black;
    }

    @media only screen and (max-width : 900px){
        .home-intro__images{
            grid-column: 1 / 3;
            grid-row: 1;
        }

        .home-intro__text{
            grid-column: 1 / 3;
            grid-row: 2;
        }

    }
</style>
