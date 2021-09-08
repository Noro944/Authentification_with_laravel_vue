<template>
  <div>
    <form @submit.prevent="handleLogin">
        <div class="row">
            <div class="col-12 col-md-2">Email : </div>
            <div class="col-6 col-md-10"><input type="text" class="form-control" v-model="form.email"></div>
            <span class="text-danger" v-if="errors.email">{{ errors.email[0] }}</span>
        </div>
        <div class="row mt-2">
         <div class="col-12 col-md-2">Password : </div>
            <div class="col-6 col-md-10"><input type="text" class="form-control" v-model="form.password"></div>    
            <span class="text-danger" v-if="errors.password">{{ errors.password[0] }}</span>
        </div>
        <button type="submit" class="btn btn-primary mt-2">Sign in</button>
    </form>
  </div>
</template>

<script>
        export default {
            data(){
                return{
                    form: {email: null, password: null},
                    errors: {}
                }
            },
            methods: {
                async handleLogin() {
                    try{
                        await axios.get('/sanctum/csrf-cookie');
                        await axios.post('/login', this.form);
                        window.location='/home';
                    } catch(error){
                        this.errors = error.response.data.errors;
                    }
                }
            }
        }
</script>
