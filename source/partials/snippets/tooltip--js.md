``` js
import { Controller } from "stimulus";

export default class extends Controller {

    static targets =["tooltip_message"]

    rightTemplate(message) {
        return `
        <span data-tooltip-target="tooltip_message" class="bg-gray-700 text-red-500 w-full text-center rounded-md py-1 px-0 absolute z-10 -top-1 left-full">${message}</span>
        `;
    }
    leftTemplate(message) {
        return `
        <span data-tooltip-target="tooltip_message" class="bg-gray-700 text-red-500 w-full text-center rounded-md py-1 px-0  absolute z-10 -top-1 right-full">${message}</span>
        `;
    }
    topTemplate(message) {
        return `
        <span data-tooltip-target="tooltip_message" class="bg-gray-700 text-red-500 w-full text-center rounded-md py-1 px-0  absolute z-10 bottom-full left-2/4 -ml-11 mb-3">${message}</span>
        `;
    }
    bottomTemplate(message) {
        return `
        <span data-tooltip-target="tooltip_message" class="bg-gray-700 text-red-500 w-full text-center rounded-md py-1 px-0  absolute z-10 top-full left-2/4 -ml-14 mt-3">${message}</span>
        `;
    }
    over(event){

        var message = event.currentTarget.dataset.tooltipTitle;
        var placement = event.currentTarget.dataset.tooltipPlacement;
        switch(placement) {
            case "right":
                event.currentTarget.insertAdjacentHTML(
                    "beforeend",
                    this.rightTemplate(message)
                );
                break;
            case "left":
                event.currentTarget.insertAdjacentHTML(
                    "beforeend",
                    this.leftTemplate(message)
                );
                break;
            case "bottom":
                event.currentTarget.insertAdjacentHTML(
                    "beforeend",
                    this.bottomTemplate(message)
                );
                break;
            case "top":
                event.currentTarget.insertAdjacentHTML(
                    "beforeend",
                    this.topTemplate(message)
                );
                break;
            default:
        }
    }

    out(){
        this.tooltip_messageTarget.remove();
    }

}

```
