<template>
    <v-dialog  max-width="600px">
        <v-btn slot="activator" class="success green">Details</v-btn>
        <v-card>
            <table style="width:100%" border="1">
                <tr>
                    <th>Item details</th>
                    <td>{{albumId}}</td>
                </tr>
                <tr>
                    <th>Item ID</th>
                    <td>{{id}}</td>
                </tr>
                <tr>
                    <th>Item Title</th>
                    <td>{{title}}</td>
                </tr>
                <tr>
                    <th>Item Image</th>
                    <td><v-img :src="thumbnailUrl" class="space" max-width="100px" max-higdth="100px"></v-img></td>
                </tr>
            </table>
        </v-card>
    </v-dialog>
</template>

<script>
 export default {
  name: 'Popup',
  props: {
    albumId: Number,
    id: Number,
    title: String,
    url: String,
    thumbnailUrl: String
  }
}
</script>


<style scoped>
</style>