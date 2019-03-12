<template>
  <form id="wizard">
    <div class="wizard__container">
      <WizardHeader />
      <WizardBody />
    </div>
  </form>
</template>

<script>
import WizardHeader from './components/WizardHeader.vue'
import WizardBody from './components/WizardBody.vue'

export default {
  name: 'wizard',
  components: {
    WizardHeader,
    WizardBody
  }
}
</script>

<style lang="stylus">
@import url('https://fonts.googleapis.com/css?family=Open+Sans:300,400,700');
primary = #fffae6
white = #fff
gray = #949494

body
  margin 0  
  padding 5rem
  background primary
  font-family 'Open Sans', sans-serif
  font-size .9rem
  color gray

h1, h2, h3, h4, h5, h6, p
  margin 0

#wizard
  color #2c3e50
  height 100%
  width 100%
  position relative

.wizard__container
  max-width 1140px
  width 100%
  padding-right 15px
  padding-left 15px
  margin-right auto
  margin-left auto
  box-sizing border-box
  padding 3rem
  background #fff

.wizard__header
  position absolute
  top -2.5rem
  left 0
  width 100%
  display flex
  justify-content center
  .wizard__step
    list-style none
    display flex
    justify-content center
    padding 1rem
    background primary
    border-radius 50px
    width 35%
    .step__list
      position relative
      &::after
          content url(./assets/icon/chevron-right.svg)
          position absolute
          top 1px
          right 0px
          width .5rem
          height .5rem
        &:nth-last-child(1)
          &::after
            display none
      a
        display flex
        justify-content start
        align-items center
        margin 0 1.5rem
        text-decoration none
        color #ff8a00
        .list__item 
          background #ffe3b9
          color white
          width 20px
          height 20px
          border-radius 50%
          font-size .65rem
          display flex
          justify-content center
          align-items center
          margin-right .5rem
          &--active
            background #ff8a00

.wizard__body
  height 100%
  width 100%
  background white
  &--content
    display grid
    grid-gap 53px
    grid-template-columns 30% 30% 30%
    .body__content
      &.body__content--left
        grid-column-start 1
        grid-column-end 3
        .delivery__header
          display flex
          justify-content space-between
          align-items center
          margin-bottom 1rem
          &--title
            color #ff8a00
          &--checkbox
            .checkbox__styled
              display block
              position relative
              padding-left: 28px
              cursor pointer
              font-size 14px
              -webkit-user-select none
              -moz-user-select none
              -ms-user-select none
              user-select none
              input
                position absolute
                opacity 0
                cursor pointer
                height 0
                width 0
                &:checked
                  ~
                    .checkmark
                      background-color white
                      border 2px solid #9ceabd
                      &:after
                        display block
              &:hover
                input
                  ~
                    .checkmark
                      background-color darken(white, 5%)
              .checkmark
                &:after
                  left 5px
                  top 3px
                  width 3px
                  height 6px
                  border solid #9ceabd
                  border-width 0 2px 2px 0
                  -webkit-transform rotate(45deg)
                  transform rotate(45deg)
            .checkmark
              position absolute
              top 0
              left 0
              height 15px
              width 15px
              background-color white
              border 2px solid #9ceabd
              &:after
                content ''
                position absolute
                display none
        .delivery__content
          display grid
          grid-gap 25px
          grid-template-columns 55% 45%
          .form__input
            padding 1.25rem
            border 1px solid #eaeaea
            color #000
            &--valid
              border 1px solid #9ceabd
              box-shadow 0px 0px 5px 0px #9ceabd
              outline none
              position relative
              background-image: url(./assets/icon/check.svg);
              background-size: 1rem 1rem;
              background-position-y: center;
              background-position-x: 95%;
              background-repeat: no-repeat
            &--invalid
              border 1px solid darken(primary, 20)
              box-shadow 0px 0px 5px 0px darken(primary, 20)
              outline none
              position relative
              background-image: url(./assets/icon/times.svg);
              background-size: 1rem 1rem;
              background-position-y: center;
              background-position-x: 95%;
              background-repeat: no-repeat
            &:focus
              border 1px solid #eaeaea
              box-shadow 0px 0px 5px 0px rgba(#ff8a00, 0.2)
              outline none
            &::placeholder
              color #aaa
          textarea
            resize none
      &.body__content--right
        display flex
        flex-direction column
        justify-content space-between
        padding-left 25px
        border-left 1px solid darken(primary, 10)
        .summary__header
          .summary__header--title
            color #ff8a00
            font-weight bold
        .summary__content
          table
            width 100%
            margin-bottom .75rem
            tbody
              tr
                td
                  padding .25rem 0
                  text-align left
                  + td
                    text-align right
          .summary__content--button
            width 100%
            padding 1rem
            background #ff8a00
            border 1px solid #ff8a00
            color white
            cursor pointer
            transition all .3s ease-in-out
            &:hover
              background darken(#ff8a00, 10)
              border 1px solid darken(#ff8a00, 10)
              transition all .3s ease-in-out




  .wizard__body--header
    margin-bottom 1.5rem
    a
      text-decoration none
      display flex
      justify-content start 
      align-items center
      color gray
      .arrow-left
        width 15px
        height 15px
        margin-right 10px
  

</style>
