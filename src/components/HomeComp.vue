<template>
    <div>
        <h1>Tickets</h1>
        <div style="display: flex; flex-wrap: wrap; justify-content: center; align-items: center;">
            <div v-for="job in jobs" :key="job.id" style="width: 300px;">
                <div style="border: 1px solid; border-radius: 10px; margin: 10px; height: 200px; padding: 30px;">
                    <h1 style="margin: 0; font-size: 18px;">
                        {{ job.title }} in {{ job.location }}
                    </h1>
                    <h3>{{ job.salary }} pesos</h3>
                    <p>"Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit..."</p>
                </div>
                
            </div>
        </div>
            
    </div>
    
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import type { PropType } from 'vue' //##
import type Job from '@/types/Job'; //##

export default defineComponent({ //##
    props: {
        jobs: {
            required: true,
            type: Array as PropType<Job[]>
        }
    }
})
</script>

<style>
</style>