<script>
    import ContactCard from "./ContactCard.svelte";
    let name = 'Jens';
    let age = 25;
    let image="";
    let description = "";
    let title="";

    $: uppercaseName = name.toUpperCase();

    $: console.log(name);
    $: if (name === 'Jensio') {
        age = 69;
    }

    function incrementAge() {
        age += 1;
    }
    function changeName(){
        name = 'Jensio'
    }

</script>
<style>
    h1 {
        color:blue;
    }
</style>


<h1>
    Hello, my name is {uppercaseName} and my age is {age}!
</h1>

<button on:click={incrementAge}>
    Bday of {name}
</button>


<label for="name">Name</label>
<input  type='text' id="name" bind:value={name} >
<label for="img">Image-url</label>
<input  type='text' id="img" bind:value={image} >
<label for="title">Title</label>
<input  type='text' id="name" bind:value={title} >
<label for="description">Job description</label>
<textarea id="description" rows="4" bind:value={description}></textarea>

<ContactCard
        userName="{name}"
        userImg="{image}"
        {description}
        title="{title}"
/>
<!-- previous
<ContactCard
        userName="{name}"
        userImg="{image}"
        description="{description}"
        title="{title}"
/>
-->

