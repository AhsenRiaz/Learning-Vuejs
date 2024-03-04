<template>
    <div class="px-2" >
        <form action="">
            <input type="text" placeholder="page title" v-model="pageTitle" >

            <div>
                <textarea name="text" id="" cols="30" rows="10" v-model="content" ></textarea>
            </div>
            <div>
                <button class="btn btn-primary"  @click.prevent="" >Create Page</button>
            </div>
        </form>
    </div>
</template>

<script>
export default{
    props:['pageCreated'],
    data(){
        return {
            pageTitle: '',
            content: ''
        }
    }
}
</script>