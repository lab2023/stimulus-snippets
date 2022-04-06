```js
import { Controller } from "@hotwired/stimulus"

export default class extends Controller {
  static targets = [ "firstTab", "tabContent" ]

  initialize() {
    this.tabIndex = 0
    this.activeTab = this.firstTabTarget
  }

  changeTab(event) {
    this.tabContentTargets[this.tabIndex].classList.add("hidden")
    this.tabIndex = event.params.id
    this.tabContentTargets[this.tabIndex].classList.remove("hidden")

    if (this.activeTab) {
      this.activeTab.classList.remove("tab-active")
    }

    event.path[0].classList.add("tab-active")

    this.activeTab = event.path[0]
  }
}
```