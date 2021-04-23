<template>
    <div>
        <div>
            <div v-if="error">
                Error: {{ error }}
            </div>
            <Suspense v-else>
                <template #default> 
                    <HelloWorld />
                </template>
                <template #fallback>
                    <div>Loading ....</div>
                </template>
            </Suspense>
        </div>
    </div>
</template>

<script>
import HelloWorld from '../components/HelloWorld.vue';

import { ref, onErrorCaptured } from 'vue';

export default {

    components: {
        HelloWorld
    },
    setup() {
        const error = ref(null);

        onErrorCaptured(e => {
            error.value = e;
            return true;
        });


        return {
            error
        }
    }

}
</script>

<style>

</style>