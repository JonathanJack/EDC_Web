<template>
    <div>
        <center>
            <div>
              <video id="vid"></video>
            </div>
            <br />
            <button id="but" v-on:click="openMirror" autoplay>
              Open WebCam
            </button>
        </center>
    </div>
</template>

<script>
   export default{
        data() {
            return{
            }
        },
        methods: {
            openMirror(){
                var but = document.getElementById("but");
                var video = document.getElementById("vid");
                var mediaDevices = navigator.mediaDevices;
                video.muted = true;
                but.addEventListener("click", () => {
                  // Accessing the user camera and video.
                  mediaDevices
                    .getUserMedia({
                      video: true,
                      audio: true,
                    })
                    .then((stream) => {
                    
                      // Changing the source of video to current stream.
                      video.srcObject = stream;
                      video.addEventListener("loadedmetadata", () => {
                        video.play();
                      });
                    })
                    .catch(alert);
                });
            }
        },
        created() {
        
        }
    }
   
</script>

<style>
div {
      width: 500px;
      height: 400px;
      border: 2px solid black;
      position: relative;
    }
    video {
      width: 500px;
      height: 400px;
      object-fit: cover;
    }
</style>
