```js
import { Controller } from "stimulus";

export default class extends Controller {
    static targets = ["image", "message"];
    static values = { size: Number };

    upload(event) {
        const file = event.target.files[0];
        if (file.size > this.sizeValue) {
            this.messageTarget.hidden = false;

        } else {
            this.messageTarget.hidden = true;

        }
        this.imageTarget.src = window.URL.createObjectURL(file);
    }
}
```
