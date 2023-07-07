<script>
  export let msg;
</script>

<div class="overlay">
    <p class="message">
      {msg.firstP}
    </p>
    <p class="message">
      {msg.secondP}
    </p>
    <p class="message">
      {msg.thirdP}
    </p>
    <p class="message">-{msg.sender}</p>
</div>

<style>
  .message {
    color: white;
    font-size: 32px;
  }

  .overlay {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    z-index: 2;
    height: 800px;
  }
</style>
