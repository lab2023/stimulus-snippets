```js
 import { Controller } from "stimulus";

export default class extends Controller {
    static targets = ["image", "modal", "backdrop", "thumbnail", "prev", "next","image_button"];

    template(image) {
        return `
    <div aria-label="Lightbox modal" class="absolute shadow-2xl top-8 max-w-3xl w-auto h-auto -translate-x-1/2 bg-white rounded mx-6 my-5 z-40" data-lightbox-target="modal">
      <div aria-label="Head" class="flex justify-between px-4 py-2">
        <h3>
          Title
        </h3>
        <button type="button" data-action="click->lightbox#close">
          Close
        </button>
      </div>
      <div aria-label="Body">
          <img src="${image}" class="max-h-96 mx-auto" data-lightbox-target="image">
      </div>
      <div aria-label="Foot" class="flex justify-between px-4 py-2">
          <button type="button" data-action="click->lightbox#prev" data-lightbox-target="prev">
           < Prev
          </button>
          <button type="button" data-action="click->lightbox#next" data-lightbox-target="next">
            Next >
          </button>
      </div>
    </div>
    <div aria-label="Backdrop" data-lightbox-target="backdrop" data-action="click->lightbox#close" class="fixed top-0 left-0 right-0 bottom-0 bg-black bg-opacity-50 z-30"></div>`;
    }

    open(event) {
        this.currentId = event.currentTarget.dataset.lightboxId;
        this.element.insertAdjacentHTML(
            "beforeend",
            this.template(event.currentTarget.dataset.lightboxImg)
        );
        document.body.classList.add("overflow-hidden");
        this.disableNext();
        this.disablePrev();
    }

    disableNext() {
        if (this.thumbnailTargets.length == this.currentId) {
            this.nextTarget.classList.add("pointer-events-none", "text-gray-300");
        }
    }

    disablePrev() {
        if (this.currentId == 1) {
            this.prevTarget.classList.add("pointer-events-none", "text-gray-300");
        }
    }

    setImg() {
        this.image_buttonTargets.map((item) => {
            if(item.dataset.lightboxId == this.currentId){
                this.imageTarget.src = item.dataset.lightboxImg;
            }
        })
    }

    prev() {
        this.currentId--;
        this.disablePrev();
        this.nextTarget.classList.remove("pointer-events-none", "text-gray-300");
        this.setImg();
    }

    next() {
        this.currentId++;
        this.disableNext();
        this.prevTarget.classList.remove("pointer-events-none", "text-gray-300");
        this.setImg();
    }

    close() {
        this.modalTarget.remove();
        this.backdropTarget.remove();
        document.body.classList.remove("overflow-hidden");
    }
}
```
