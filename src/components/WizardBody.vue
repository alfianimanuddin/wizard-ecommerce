<template>
    <div class="wizard__body">
        <div class="wizard__body--header">
          <a href="/">
            <img class="arrow-left" src="../assets/icon/arrow-left.svg" alt="">
            Back to cart
          </a>
        </div>
        <div class="wizard__body--content">
          <div class="body__content body__content--left">
            <div class="delivery__header">
              <h1 class="delivery__header--title">
                Delivery Details
              </h1>
              <div class="delivery__header--checkbox">
                <label class="checkbox__styled">Send as dropshipper
                  <input type="checkbox" v-on:click="checkboxToggle">
                  <span class="checkmark"></span>
                </label>
              </div>
            </div>
            <div class="delivery__content">
              <input class="form__input" type="text" placeholder="Name">
              <input class="form__input" id="dropshipper-name" type="text" placeholder="Dropshipper Name">
              <input class="form__input" type="number" placeholder="Phone Number">
              <input class="form__input" id="dropshipper-phone" type="number" placeholder="Dropshipper Phone Number">
              <textarea class="form__input" cols="30" rows="5" placeholder="Delivery Address"></textarea>
            </div>
          </div>
          <div class="body__content body__content--right">
            <div class="summary__header">
              <h2 class="summary__header--title">
                Summary
              </h2>
              <p class="summary__header--description">
                10 items purchased
              </p>
            </div>
            <div class="summary__content">
              <table>
                <tbody>
                  <tr>
                    <td>Cost of goods</td>
                    <td>500,000</td>
                  </tr>
                  <tr>
                    <td>Dropshipping Fee</td>
                    <td>5,900</td>
                  </tr>
                  <tr>
                    <td>
                      <h4>
                        Total
                      </h4>
                    </td>
                    <td>
                      <h4>
                        505,900
                      </h4>
                    </td>
                  </tr>
                </tbody>
              </table>
              <button class="summary__content--button" v-on:click="submit">
                Continue to Payment
              </button>
            </div>
          </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "WizardBody",
    data: {
        checkboxToggle: true
    },
    methods: {
        submit: function (event) {
            alert('Submitted!')
        },
        
        checkboxToggle: function (event) {
            let dropshipperName = document.getElementById('dropshipper-name');
            let dropshipperPhone = document.getElementById('dropshipper-phone');

            dropshipperName.setAttribute("disabled", "");
            dropshipperPhone.setAttribute("disabled", "");
        }
    }
}
</script>

<style lang="stylus" scoped>

</style>
