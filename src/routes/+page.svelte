<script>
  import Useless_Image from "./images/delete_this/linux.webp"
  import ToolCard from "./components/ToolCard.svelte";

  let description_for_dragon = "It's a dragon I downloaded from the Internet because I'm lazy. Please help.";
</script>

<ToolCard name="Dragon" description={description_for_dragon} image={Useless_Image} link="./delete_this" />
