// eslint-disable-next-line vue/script-setup-uses-vars
<template>
    <div class="vue-tempalte">
        <form>
            <h3>Sign In</h3>

            <div class="form-group">
                <label>Usuário</label>
                <input type="email" class="form-control form-control-lg" />
            </div>

            <div class="form-group">
                <label>Senha</label>
                <input type="password" class="form-control form-control-lg" />
            </div>
      
        <button type="submit"  @click="onLogin" class="btn btn-dark btn-lg btn-block">Entrar</button>
            
       
            

        </form>
    </div>
</template>

<script>
    import axios from 'axios';
    export default {
        data() {
            return {}
        },
        methods: {
            onLogin(){
                
            const path = "http://3.134.97.232:1717/embedded"
              const headers = {
                "Content-Type": "application/json"
              };
            axios.post(path, {
              method:"<INIT>",
              classroom: "6186c50e995ba73d671de797"
        },{headers}).then(async(response) => {
              const res = await response
              // eslint-disable-next-line no-console
              console.log(res)
        });
        }
        },
    }

</script>