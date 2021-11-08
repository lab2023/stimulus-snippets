``` js
import { Controller } from "stimulus";

export default class extends Controller {
    static targets =["notification_list"]

    openToggle(){
        this.notification_listTarget.classList.toggle("hidden");
    }
}

```
