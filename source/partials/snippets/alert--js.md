```js
import { Controller } from "stimulus";

export default class extends Controller {
    closeAlert (){
        this.element.remove();
    }
}
```
