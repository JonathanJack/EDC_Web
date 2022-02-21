<template>
    <button v-on:click="saveFile">teste</button>
</template>

<script>
import {saveAs} from 'file-saver';
    FileSaver saveAs(Blob/File/Url, optional DOMString filename, optional Object { autoBom: true });

    export default{       
        methods: {
            saveFile(){
                var blob = new Blob(["teste"],{type: "text/plain;charset=utf-8"});

                FileSaver.saveAs(blob,"testfile1.txt");
            }
        }
    }

</script>

<style></style>