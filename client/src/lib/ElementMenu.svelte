<script lang="ts">
  export let type: string = '';
  let numInArray: number = 0;
  let menuList: string[] = [];
  export let selectedValue: string;

  $: {
    if (type == 'ator') {
      menuList = ['atorKomentator', 'atorZielon', 'atorJackowski'];
    } else if (type == 'bg') {
      menuList = ['corona'];
    } else if (type == 'elements') {
      menuList = ['alien1', 'biden1', 'kaczorKrol', 'klausSchwab1'];
    }
    selectedValue = menuList[numInArray];
  }

  const up = () => {
    if (numInArray < menuList.length - 1) {
      numInArray += 1;
    } else {
      numInArray = 0;
    }
  };

  const down = () => {
    if (numInArray > 0) {
      numInArray -= 1;
    } else {
      numInArray = menuList.length - 1;
    }
  };
</script>

<button on:click={up} class="upBtn">👆</button>

<img width="200px" src={`images/${type}/${menuList[numInArray]}.webp`} alt="" />

<button on:click={down} class="downBtn">👇</button>