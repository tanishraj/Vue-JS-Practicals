<template>
    <div class="col-xs-12 col-sm-6">
        <ul class="list-group">
            <app-server v-for="server in servers" :server="server" :key="server.id"></app-server>
        </ul>
    </div>
</template>

<script>
import Server from './Server.vue';

export default {
    data: function(){
        return{
            servers: [
                {'id': 1, 'status':'Normal', 'notification': 'text-success'},
                {'id': 2, 'status':'Busy', 'notification': 'text-warning'},
                {'id': 3, 'status':'Blocked', 'notification': 'text-danger'},
                {'id': 4, 'status':'Not Reachable', 'notification': 'text-danger'},
                {'id': 5, 'status':'Unknown', 'notification': 'text-warning'}
            ]
        }
    },

    components: {
        appServer: Server
    }
}

</script>