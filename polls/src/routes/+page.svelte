<script>
    import Header from "./components/header.svelte";
    import Footer from "./components/footer.svelte";
    import Tabs from "./shared/tabs.svelte";

    //tabs
    let items = ['Current Polls', 'Add New Poll']
    let activeItem = 'Current Polls'
</script>


    <body>
        <Header></Header>
        <main>
           <Tabs {activeItem} {items}/>
        <Footer></Footer>
    </body>


<style>
    body{
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        overflow-x: hidden;
    }
    main{
        max-width: 960px;
        margin: 40px auto;
    }
</style>