<template>
    <div class="v-coding-form">
        <header>
            <h2>{{name}}</h2>
        </header>

         <v-select :items="algorithms"
                   color="#ffffff"
                   :label="selectLabel">
        </v-select>
    </div>
</template>

<script>
export default {
    name: "v-coding-form",
    data (){
        return {
             algorithms: [
                 'Morse code',
                 'Caesar\'s code',
                 'Atbash Cipher',
                 'Vernam cipher',
                 'Codeword Code',
                 'Playfer Code'
             ],
        }
    },
    computed: {
        name (){
            return (this.$route.path + ' form').slice(1);
        },
        selectLabel (){
            return `Alogorithm of ${this.$route.path.slice(1, this.$route.path.length - 1)}ing`;
        } 
    }
}
</script>

<style lang="scss">
    .v-coding-form {
        width: 100%;

        & header {
            font: 400 24px 'Fira Code', sans-serif;
            text-align: center;
            color: #ffffff;

            & h2 {
                font-weight: 400;
            }

            & h2:first-letter {
                text-transform: uppercase;
            }
        }
    }

    div.v-coding-form .theme--light.v-label, .theme--light.v-icon {
        color: #ffffff;
    }

    div.v-input__control::hover {
         & .v-input__slot:before {
            border-color: #ffffff;
        }
    }

    div.theme--light.v-text-field > .v-input__control > .v-input__slot:before {
        transition: none;
        border-color: #ffffff;

       
    }

    div.v-text-field.v-input--is-focused > .v-input__control > .v-input__slot:after {
        transition: none;
        transform: none;
    }
</style>