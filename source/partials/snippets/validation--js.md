```js

 import { Controller } from "stimulus";

export default class extends Controller {
    static targets = ["input", "message"];
    static classes = ["hidden", "error"];


    connect () {
        this.element.setAttribute('novalidate', true)
        this.element.addEventListener('blur', this.onBlur, true)
        this.element.addEventListener('submit', this.onSubmit)
        this.element.addEventListener('ajax:beforeSend', this.onSubmit)
    }

    disconnect () {
        this.element.removeEventListener('blur', this.onBlur)
        this.element.removeEventListener('submit', this.onSubmit)
        this.element.removeEventListener('ajax:beforeSend', this.onSubmit)

        this.inputTargets.forEach((element) => {
            element.setAttribute("aria-invalid", false);
            element.classList.remove("form__input--error");
        });
        this.messageTargets.map((element) => element.remove());
    }

    onBlur = (event) => {
        this.validity(event);
    }

    onSubmit = (event) => {

        this.formFields.forEach((field) => {
            this.messageTargets.map((item) => {
                if (item.dataset.id === field.id) {
                    item.classList.add(this.hiddenClass);
                }
            });
            field.setAttribute("aria-invalid", false);
            if(!field.checkValidity())
            {
                event.preventDefault();
                field.insertAdjacentHTML(
                    "afterend",
                    this.template(field.id, field.dataset.inputMessage)
                );
                field.setAttribute("aria-invalid", true);
            }
        })

    }

    template(id, message) {
        return `
        <div class="${this.errorClass}" data-validation-target="message" data-id="${id}">
          <small>
            ${message}
          </small>  
        </div>
      `;
    }



    initialize() {

        this.inputTargets.forEach((element) => {

            if (JSON.parse(element.getAttribute("aria-invalid"))) {
                if (JSON.parse(element.dataset.inputHasAddon)) {
                    element.parentElement.insertAdjacentHTML(
                        "afterend",
                        this.template(element.id, element.dataset.inputMessage)
                    );
                } else {
                    element.insertAdjacentHTML(
                        "afterend",
                        this.template(element.id, element.dataset.inputMessage)
                    );
                }
            }
        });
    }

    validity(event) {

        var element = event.currentTarget;
        if (JSON.parse(event.currentTarget.getAttribute("aria-invalid"))) {

            this.removeErrorMessage(event);

            if (event.currentTarget.validity.valid && element.value) {
                event.currentTarget.setAttribute("aria-invalid", false);
            }
            else {
                this.addErrorMessage(event)
            }
        }
        else if (element.hasAttribute("required") && element.value === "")
        {
            this.addErrorMessage(event)
        } else if (element.type === "checkbox" && element.hasAttribute("required") && element.checked === false){
            this.addErrorMessage(event)
        }
    }


    get formFields () {
        return Array.from(this.element.elements)
    }


    addErrorMessage(event){
        event.currentTarget.insertAdjacentHTML(
            "afterend",
            this.template(event.currentTarget.id, event.currentTarget.dataset.inputMessage)
        );
        event.currentTarget.setAttribute("aria-invalid", true);
    }

    removeErrorMessage(event){

        this.messageTargets.map((item) => {
            if (item.dataset.id === event.currentTarget.id) {
                item.classList.add(this.hiddenClass);
            }
        });
    }
}

```
