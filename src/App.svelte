<script>
  import NavBar from "./NavBar.svelte";
  import AddNewMember from "./AddNewMember.svelte";
  import MemberCard from "./MemberCard.svelte";

  let toggleAddNewMember = false;

  //  aLL the players
  let allThePlayers = [
    {
      name: "Ismael Garcia",
      imageSrc: "https://loremflickr.com/300/200",
      score: 200
    },
    {
      name: "Miguel Gutierrez",
      imageSrc: "https://loremflickr.com/300/210",
      score: 4545
    },
    {
      name: "Oscar Lopez",
      imageSrc: "https://loremflickr.com/300/230",
      score: 23423
    },
    {
      name: "Jose Villalpando",
      imageSrc: "https://loremflickr.com/300/201",
      score: 2045340
    }
  ];

  const openForm = () => (toggleAddNewMember = !toggleAddNewMember);
  const addMember = e => {
    const newMember = e.detail;
    allThePlayers = [...allThePlayers, newMember];
  };
</script>

<style>
  .container {
    max-width: 1200px;
    margin: 0 auto;
    text-align: center;
    padding: 2rem 1rem;
  }
  .form-container {
    min-height: 200px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  .info {
    margin-top: 1rem;
  }
  .cards {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
  }
</style>

<NavBar />

<div class="container">
  <div class="form-container">
    <button class="btn btn-main" on:click={openForm}>
      {#if toggleAddNewMember}Close Form{:else}Open Form{/if}
    </button>
    {#if toggleAddNewMember}
      <AddNewMember on:addmember={addMember} />
    {:else}
      <p class="info yellow">Add new member to this awesome group</p>
    {/if}
  </div>

  <!-- Loop for all the members -->
  {#if allThePlayers.length === 0}
    <h2>Please add a player to the list</h2>
  {:else}
    <div class="cards">
      {#each allThePlayers as member}
        <MemberCard
          name={member.name}
          score={member.score}
          imageSrc={member.imageSrc} />
      {/each}
    </div>
  {/if}
</div>
