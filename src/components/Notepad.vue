<template>
<div>
    <textarea id="notepad" @change="saveNotepadText"></textarea>
    <!-- <button v-on:click="saveNotepadText">Salvar</button> -->
</div>
</template>

<script>

    export default{       
        methods: {
            saveNotepadText(){
                let txtNotepad = document.getElementById("notepad").value;
                localStorage.setItem('notepad',txtNotepad);
            },
            readLocalStorage(){
                let notepad = document.getElementById("notepad");
                let txtNotepad = localStorage.getItem('notepad');
                notepad.value = txtNotepad;
            }

        },
        mounted(){
            this.readLocalStorage();
        }
    }

</script>

<style></style>