<script>
    import Header from "./components/header.svelte";
    import Footer from "./components/footer.svelte";
    import Tabs from "./shared/tabs.svelte";
    import Createpoll from "./components/createpoll.svelte";

    //tabs
    let items = ['Current Polls', 'Add New Poll']
    let activeItem = 'Current Polls'

    const tabChange = (e) => {
        activeItem = e.detail
    }
</script>


    <body>
        <Header></Header>
        <main>
           <Tabs {activeItem} {items} on:tabChange={tabChange}/>
           {#if activeItem === 'Current Polls'}
            <p>Poll list component goes here</p>
            {:else if activeItem === 'Add New Poll'}
                <Createpoll/>
           {/if}
        </main>
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