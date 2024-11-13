<script setup>
import{ref} from 'vue';

defineProps({

    name: {
        type: String,
        required: true
    }
}

)


const selected = ref (false);


const selectPlan= () ==> {
 selected.value = true;
}
</script>

