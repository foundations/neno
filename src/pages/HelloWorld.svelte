<script>
  import SideLeft from "./SideLeft.svelte";
  import SideRight from "./SideRight.svelte";
  import Setting from "./Setting.svelte";
  import SettingSlide from "./SettingSlide.svelte";
  import NenoDetail from "../components/NenoDetail.svelte";
  import ViewPicture from "../components/ViewPicture.svelte";
  import Daily from "./Daily.svelte";
  import Share from "../components/Share.svelte";

  import { paged } from "../store/store.js";
  import { settingStore } from "../store/store.js";
</script>

<div class:dark={$settingStore.isDark} class=" overflow-visible">
  <div
    class="w-full  h-screen flex flex-col items-center justify-start  bg-gray-100 dark:bg-black   overflow-visible"
  >
    <div class="max-w-6xl min-w-0 w-full  flex   overflow-visible ">
      <div
        class="hidden  sm:flex md:flex flex-col items-start dark:bg-black  overflow-visible"
        style="width:240px"
      >
        <SideLeft />
      </div>
      {#if $paged === "neno"}
        <SideRight />
      {:else if $paged === "setting"}
        <Setting />
      {:else}
        <Daily />
      {/if}
    </div>
    <NenoDetail />
    <SettingSlide />
    <ViewPicture />
    <Share />
  </div>
</div>
