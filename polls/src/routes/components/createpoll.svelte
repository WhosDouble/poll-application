<script>
    import Button from "../shared/button.svelte";
    let fields = {
        question: "",
        answerA: "",
        answerB: "",
    };

    const handleSubmit = () => {
        console.log(fields);
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <div class="form-field">
        <label for="question">
            Poll Question
        </label>
        <input type="text" id="question" bind:value={fields.question}>
    </div>
    <div class="form-field">
        <label for="answer-a">
            Answer a
        </label>
        <input type="text" id="answer-a" bind:value={fields.answerA}>
    </div>
    <div class="form-field">
        <label for="answer-b">Answer b</label>
        <input type="text" id="answer-b" bind:value={fields.answerB}>
        <div class="btn-container">
            <Button type='secondary'>Add Poll</Button>
        </div>
    </div>
</form>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Anton+SC&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');
    form{
        width: 400px;
        margin: 0 auto;
       
    }
    .form-field{
        margin-bottom: 30px;
    }
    .btn-container{
        display: flex;
        justify-content: center;
        margin: 25px;
    }
    label{
       font-size: 18px;
       font-weight: 400;
       font-family: Poppins, sans-serif;
    }
    input{
        width: 100%;
        border-radius: 5px;
        border: 1.5px solid;
        padding: 10px;
    }
</style>