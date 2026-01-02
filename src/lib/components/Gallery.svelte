<script>
  import Autoplay from 'embla-carousel-autoplay';
  import emblaCarouselSvelte from 'embla-carousel-svelte';

  let options = { loop: true, align: 'center' }
  // Stop autoplay on interaction is default, but we can verify behavior
  let plugins = [Autoplay({ delay: 3000, stopOnInteraction: true })]
  
  let emblaApi
  const TWEEN_FACTOR_BASE = 0.20
  let tweenFactor = 0
  let tweenNodes = []

  const numberWithinRange = (number, min, max) =>
    Math.min(Math.max(number, min), max)

  const setTweenNodes = (api) => {
    tweenNodes = api.slideNodes().map((slideNode) => {
      return slideNode.querySelector('img')
    })
  }

  const setTweenFactor = (api) => {
    tweenFactor = TWEEN_FACTOR_BASE * api.scrollSnapList().length
  }

  const tweenScale = (api, eventName) => {
    const engine = api.internalEngine()
    const scrollProgress = api.scrollProgress()
    const slidesInView = api.slidesInView()
    const isScrollEvent = eventName === 'scroll'

    api.scrollSnapList().forEach((scrollSnap, snapIndex) => {
      let diffToTarget = scrollSnap - scrollProgress
      const slidesInSnap = engine.slideRegistry[snapIndex]

      slidesInSnap.forEach((slideIndex) => {
        if (isScrollEvent && !slidesInView.includes(slideIndex)) return

        if (engine.options.loop) {
          engine.slideLooper.loopPoints.forEach((loopItem) => {
            const target = loopItem.target()

            if (slideIndex === loopItem.index && target !== 0) {
              const sign = Math.sign(target)

              if (sign === -1) {
                diffToTarget = scrollSnap - (1 + scrollProgress)
              }
              if (sign === 1) {
                diffToTarget = scrollSnap + (1 - scrollProgress)
              }
            }
          })
        }

        const tweenValue = 1 - Math.abs(diffToTarget * tweenFactor)
        const scale = numberWithinRange(tweenValue, 0, 1).toString()
        const tweenNode = tweenNodes[slideIndex]
        if (tweenNode) {
          tweenNode.style.transform = `scale(${scale})`
        }
      })
    })
  }

  const onInit = (event) => {
    emblaApi = event.detail
    
    setTweenNodes(emblaApi)
    setTweenFactor(emblaApi)
    tweenScale(emblaApi)

    emblaApi
      .on('reInit', setTweenNodes)
      .on('reInit', setTweenFactor)
      .on('reInit', tweenScale)
      .on('scroll', tweenScale)
      .on('slideFocus', tweenScale)
  }
</script>

<section id="gallery" class="section light-bg">
  <div class="container">
    <div class="section-title">
      <small>GALLERY</small>
      <h3>App Screenshots</h3>
    </div>
    
    <div class="embla" use:emblaCarouselSvelte={{ options, plugins }} on:emblaInit={onInit}>
      <div class="embla__container">
        <div class="embla__slide">
          <img src="/images/screen1.png" alt="App Screen 1">
        </div>
        <div class="embla__slide">
          <img src="/images/screen2.png" alt="App Screen 2">
        </div>
        <div class="embla__slide">
          <img src="/images/screen3.png" alt="App Screen 3">
        </div>
        <div class="embla__slide">
          <img src="/images/screen4.png" alt="App Screen 4">
        </div>
        <div class="embla__slide">
          <img src="/images/screen5.png" alt="App Screen 5">
        </div>
      </div>
    </div>
  </div>
</section>

<style>
  .embla {
    overflow: hidden;
    padding: 1rem 0; /* Space for shadow */
    margin: 0 auto;
    max-width: 100%;
  }
  
  .embla__container {
    display: flex;
    gap: 2rem;
  }
  
  .embla__slide {
    flex: 0 0 auto;
    min-width: 0;
  }
  
  .embla__slide img {
    display: block;
    max-height: 500px;
    width: auto;
    border-radius: 10px;
    box-shadow: 0 9px 32px 0px rgba(0, 0, 0, 0.07);
    /* Transition removed so JS can tween smoothly */
  }
</style>
