<script>
    import Header from "./components/header.svelte";
    import Footer from "./components/footer.svelte";
    import Tabs from "./shared/tabs.svelte";
    import Createpoll from "./components/createpoll.svelte";
    import PollList from "./components/PollList.svelte";

    //tabs
    let items = ['Current Polls', 'Add New Poll']
    let activeItem = 'Current Polls'

    const tabChange = (e) => {
        activeItem = e.detail
    }

    let polls = [
        {
            id:1,
            question: 'Python or JavaScript?',
            answerA:'Python',
            answerB: 'JavaScript',
            votesA: 12,
            votesB: 23,
        }
    ]

    const handleAdd = (e) => {
        const poll = e.detail;
        polls = [poll, ...polls]
        activeItem = 'Current Polls'
        console.log(polls);
    }

    const handleVote = (e) => {
        const { id, option } = e.detail

        let copiedPolls = [...polls ];
        let upVotedPoll = copiedPolls.find((poll) => poll.id = id)

        if(option === 'a') {
            upVotedPoll.votesA++
        }
        if(option === 'b') {
            upVotedPoll.votesB++
        }

        polls = copiedPolls
    }
</script>


    <body>
        <Header></Header>
        <main>
           <Tabs {activeItem} {items} on:tabChange={tabChange}/>
           {#if activeItem === 'Current Polls'}
            <PollList {polls} on:vote={handleVote}/>
            {:else if activeItem === 'Add New Poll'}
                <Createpoll on:add={handleAdd}/>
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