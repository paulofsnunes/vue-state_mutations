<template>
    <div>
        <p>Aula {{totalAulas}}, esse é o usuário: {{user}}, {{aulasCompletas}}</p>
        <button @click="handleClick">Modificar Usuário</button>
        <button @click="COMPLETAR_AULA">Completar Aula</button>
        <input type="text" v-model="novoUser">
    </div>
</template>

<script>

import { mapState, mapMutations } from "vuex"

export default {
    data() {
        return {
            totalAulas: 25,
            nome: "Paulo",
            novoUser: ""
        }
    },
    computed: {
        ...mapState(["user", "aulasCompletas"]),
        nomeMaiusculo() {
            return this.nome.toUpperCase()
        }
    },
    // {
    //     user() {
    //         return this.$store.state.user
    //     },
    //     aulasCompletas() {
    //         return this.$store.state.aulasCompletas
    //     }
    // },
    methods: {
        ...mapMutations(["CHANGE_USER", "COMPLETAR_AULA"]),
        handleClick() {
            this.CHANGE_USER({
                user: this.novoUser,
                totalAulas: this.totalAulas
            })
        },
        // completar() {
        //     this.completarAula()
        // ou
        //     this.$store.commit("completarAula")
        // }
    }
}
</script>

<style>

</style>