<template>
    <textarea id="notepad" @change="saveNotepadText"></textarea>
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