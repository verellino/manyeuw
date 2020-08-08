<template>
<section class="yt-section container">
    <h2 class="ttl">SEKILAS MANYEUW</h2>
    <div class="video-youtube">
        <iframe class="vyt" src="https://www.youtube.com/embed/NgYaEdaarYY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        <iframe class="vyt" src="https://www.youtube.com/embed/ORrPhiKQsFk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div>  
    <div class="video-youtube">
        <iframe class="vyt" src="https://youtube.com/embed/628ppkphnSs/" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
        <iframe class="vyt" src="https://youtube.com/embed/W4sIf_SUbMc/" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
    </div> 
    <br>
    <a href="https://www.youtube.com/channel/UCyk22T9gyn4vk6EWrBacqUg/"><h3>Lihat selengkapnya di kanal youtube kami..</h3></a>
    <iframe class="gmaps" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d63517.907162310665!2d132.60565493170367!3d-5.731972436475151!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2d300210c20108d5%3A0x759039d1fd6358e2!2sManyeuw%2C%20Sotheast%20Maluku%20Regency%2C%20Maluku!5e0!3m2!1sen!2sid!4v1596899117731!5m2!1sen!2sid" width="600" height="450" frameborder="0" style="border:0;" allowfullscreen="" aria-hidden="false" tabindex="0"></iframe>
</section>
</template>

<script>
export default {
    name: 'video-youtube',
}
</script>

<style>
.yt-section{
    margin: 150px auto;
    text-align: center;
}
.ttl {
    margin-bottom: 50px;
    }
.video-youtube{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 10px;
}
.vyt{
    width: 49.8%;
    height: 265px;
}
.gmaps{
    width: 100%;
    margin: 20px 0;
}
@media (max-width: 767px)  {
    .video-youtube{
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-between;
    }
    .vyt{
        width: 100%;
        height: calc(150px * 0.48vw);
        margin-bottom: 20px;
    }
}
</style>