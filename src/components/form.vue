<template>
<div class="form-component">
     <div class="sale">
        <div class="sale__wrapper">
            try in free 7 days <span>thin 520/mo. theriatter</span>
        </div>
     </div>
     <div class="sale">
        <div class="sale__wrapper sale__wrapper--mobile">
            try in free 7 days <span>thin <br/> 520/mo. theriatter</span>
        </div>
     </div>
  <form  id="form" class="form" @submit.prevent="submitForm">
      <div class="form__wrapper">

          <div class="form__input">
              <input type="text" placeholder="First Name" v-model="state.firstName" >
              <img v-if="v$.firstName.$error && v$.lastName.$dirty"  class ='errorImg' src="../assets/images/icon-error.svg" alt="errorImg">
            
          </div>
           <div class="massage-error">
                <i v-if="v$.firstName.$error && v$.lastName.$dirty">First Name connect be empty </i>
                </div> 
        <div class="form__input">
              <input type="text" placeholder="Last Name" v-model="state.lastName">
              <img  v-if="v$.lastName.$error && v$.lastName.$dirty" class ='errorImg' src="../assets/images/icon-error.svg" alt="errorImg">
          </div>
            <div class="massage-error">
                <i v-if="v$.lastName.$error && v$.lastName.$dirty">Last Name connect be empty </i>
                </div> 
          <div class="form__input">
              <input type="text" placeholder="Email Address" v-model="state.email" >
              <img   class ='errorImg' src="../assets/images/icon-error.svg" alt="errorImg"  v-if="v$.email.$error && v$.email.$dirty">
              
          </div>

          <div class="error-massage" v-if="v$.email.$error && v$.lastName.$dirty">
                <div v-for="error of v$.email.$errors" :key="error.$uid">
                    <i v-if="error.$validator == 'email'"> Look like this is not an email</i>
                    <i v-else> Email connect be empty </i>

                     
                </div>
            </div>
           
           

          <div class="form__input">
              <input type="text" placeholder="Password" v-model="state.password">
              <img  v-if="v$.password.$error && v$.password.$dirty" class ='errorImg' src="../assets/images/icon-error.svg" alt="errorImg">
              
          </div>
            <div class="massage-error">
                  <i v-if="v$.password.$error && v$.password.$dirty">Last Name connect be empty </i>
                </div> 

          <div class="btn-wrapper">
          <button class="button">cleim to free trial</button>
      </div>
       
      <div class="form__massage">
        By clicking the button, you are agreing  to our 
        <span>Terms end servises</span>
        </div>
         <div class="form__massage  form__massage-mobile">
        By clicking the button, you are agreing  to<br/> our
        <span>Terms end servises</span>
        </div>
        
      </div>
      
     
  </form>
  </div>
</template>

<script>
import { reactive} from '@vue/composition-api' 
import useVuelidate from '@vuelidate/core'
import { required, email } from '@vuelidate/validators'
export default {
    setup () {
    const state = reactive({
      firstName: '',
      lastName: '',
       email: '',
      password:'',
      
    })
    const rules = {
      firstName: { required }, 
      lastName: { required }, 
      email: { required, email },
      password:{ required,} 

      
    }

    const v$ = useVuelidate(rules, state)
    function submitForm(){
        console.log(v$)
        if (v$.value.$invalid) {
            v$.value.$touch()
            return
            
        }
    }
    return { state, v$, submitForm }
  }
}
    
</script>