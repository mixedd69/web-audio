<template>
  <div class="music-player-container">

		<div class="music-player">
			<div class="player-content-container">
				<h1 class="artist-name">Incubus</h1><!--  /.track-title -->
				<h2 class="album-title">Make Yourself</h2><!--  /.album-title -->
				<h3 class="song-title">"Stellar"</h3><!--  /.song-title -->
				<div class="music-player-controls">
					<div class="control-play">
            <i class="fas fa-play"></i>
          </div><!--  /.control-play -->
          <div class="control-pause is-visible">
            <i class="fas fa-pause"></i>
          </div><!-- /.control-pause -->
					<div class="control-stop">
            <i class="fas fa-stop"></i>
          </div><!--  /.control-forwards -->
				</div><!--  /.music-player-controls -->
			</div><!--  /.player-content-container -->
		</div><!--  /.music-player -->

		<div class="album">
			<div class="album-art"></div><!--  /.album-art -->
			<div class="vinyl"></div><!--  /.vinyl -->
		</div><!--  /.album-art -->

  </div><!--  /.music-player -->

</template>

<script>
export default {
  name: "MusicPlayer"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.music-player-container {
  transform: translate(-50%, -50%);
  display: inline-block;
  height: 370px;
  position: absolute;
  min-width: 460px;
  left: 50%;
  top: 50%;

  &:after {
    filter: blur(8px);
    background-color: rgba(0, 0, 0, 0.8);
    bottom: -2px;
    content: " ";
    display: block;
    height: 10px;
    left: 19px;
    position: absolute;
    transform: rotate(-3deg);
    width: 70%;
    z-index: 0;
  }
}

.music-player {
  background-color: #fff;
  height: 370px;
  padding: 40px 250px 40px 40px;
  position: absolute;
  text-align: right;
  width: 460px;
  z-index: 3;
} // .music-player

.player-content-container {
  transform: translateY(-50%);
  top: 50%;
  position: relative;
} // .player-content-container

.artist-name {
  font-size: 28px;
  font-weight: normal;
  margin: 0 0 0.75em 0;
} // .artist-name

.album-title {
  font-weight: 200;
  font-size: 24px;
  margin: 0 0 1.75em 0;
} // .album-title

.song-title {
  font-size: 18px;
  font-weight: 200;
  margin: 0 0 1.5em 0;
} // .song-title

.album {
  box-shadow: 3px 3px 15px rgba(0, 0, 0, 0.65);
  height: 315px;
  margin-left: 250px;
  margin-top: 27px;
  position: relative;
  width: 315px;
  z-index: 10;
} // .album

.album-art {
  background: #fff
    url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/83141/incubus-make-yourself.jpg")
    center / cover no-repeat;
  height: 315px;
  position: relative;
  width: 315px;
  z-index: 10;
}

.vinyl {
  animation: spin 2s linear infinite;
  transition: all 500ms;
  background-image: url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/83141/vinyl.png"),
    url("https://s3-us-west-2.amazonaws.com/s.cdpn.io/83141/incubus-make-yourself.jpg");
  background-position: center, center;
  background-size: cover, 40% auto;
  background-repeat: no-repeat;
  border-radius: 100%;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.8);
  height: 300px;
  left: 0;
  position: absolute;
  top: 5px;
  width: 300px;
  z-index: 5;
  will-change: transform, left;

  .playing & {
    left: 52%;
  }
}

.music-player-controls {
  text-align: center;
} // .music-player-controls

[class^="control-"] {
  filter: brightness(95%);
  display: inline-block;
  font-size: 1.5em;
  height: 44px;
  margin: 0 3px;
  width: 60px;

  &:hover {
    filter: brightness(85%);
    cursor: pointer;
  } // :hover
} // [class^="control-"]

.control-play {
  .playing & {
    //display: none;
  } // .control-play
} // .control-play

.control-pause {
}

.is-visible {
  display: none;
}
@keyframes spin {
  0% {
    transform: rotate(0deg);
  }
  100% {
    transform: rotate(360deg);
  }
}
</style>
