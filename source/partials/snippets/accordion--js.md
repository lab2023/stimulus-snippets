``` js
import { Controller } from "stimulus";

export default class extends Controller {
    static targets = ["accordion"]
    accordionToggle(event)
    {
        console.log(event.currentTarget.dataset);
        this.accordionTargets.map((item) => {

            if (item.dataset.accordionId === event.currentTarget.dataset.accordionId) {

                item.classList.toggle("hidden")

            }else {
                item.classList.add("hidden")
            }
        });
    }
}
```
