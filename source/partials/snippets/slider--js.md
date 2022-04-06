```js
import { Controller } from "@hotwired/stimulus"

export default class extends Controller {
  static targets = [ "slide"]
  static values = {
    auto: Boolean,
    speed: Number
  }

  initialize() {
    this.index = 0
    this.autoMouse = true
  }

  connect() {
    this.play()
  }

  disconnect() {
    this.stop()
  }

  play() {
    this.refreshTimer = setInterval(() => {
      if (this.autoValue == true && this.autoMouse == true ) {
        this.next()
      }
    }, this.speedValue)
  }

  stop() {
    if (this.refreshTimer) {
      clearInterval(this.refreshTimer)
    }
  }

  mouseOver() {
    this.autoMouse = false
  }

  mouseOut() {
    this.autoMouse = true
  }

  next() {
    this.slideTargets[this.index].classList.add("hidden")

    this.index++
    this.index = this.index % this.slideTargets.length

    this.slideTargets[this.index].classList.remove("hidden")
  }

  prev() {
    this.slideTargets[this.index].classList.add("hidden")

    this.index--
    if (this.index < 0 ) {
      this.index = this.slideTargets.length-1
    }

    this.slideTargets[this.index].classList.remove("hidden")

  }
}
```
