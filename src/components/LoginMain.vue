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
                
            const path = "chamadarfid.ddns.net:9090/init_attendance"
            axios.post(path, {
            token: "eyJhbGciOiJIUzI1NiIsInR5cCI6ImFjY2VzcyJ9.eyJpYXQiOjE2MzgyMjg5MDEsImV4cCI6MTYzODMxNTMwMSwiYXVkIjoiaHR0cHM6Ly95b3VyZG9tYWluLmNvbSIsImlzcyI6ImZlYXRoZXJzIiwic3ViIjoiNjE4MTcyN2VkMjMxYmQwMzY0NDkyMWJkIiwianRpIjoiZTEzZTI3Y2ItODNkMy00YWYzLTgzNjgtYjI0ZmE5ZGVlMWFhIn0.sJWvtvJANUeT5DIXvw4zAH_b2xNMiBzJ9euNh9ZrOxA",
            classroom: "6186c50e995ba73d671de797",
        }).then((response) => {
            this.makeToast(response); this.$parent.changeContext(response);
        });
        }
        },
    }

</script>