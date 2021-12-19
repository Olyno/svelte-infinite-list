# svelte-infinite-list

Create an infinite list of items with optimized rendering.

## Installation

```shell
npm i --save-dev svelte-infinite-list # or yarn add -D svelte-infinite-list
```

## Usage

```svelte
<script>
  const alphabet = 'abcdefghijklmnopqrstuvwxyz'.split('')
</script>

<AsyncList
  class="h-full w-full hide-scroll"
  items={alphabet}
  itemsLoaded={5}
  let:item
>
  <p>{item}</p>
</AsyncList>
```

## Buy me a ko-fi

Whether you use this project, have learned something from it, or just like it, please consider supporting it by buying me a coffee, so I can dedicate more time on open-source projects like this 😉 (personally I prefer hot chocolate but whatever)

[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/olyno)

## License

Code released under GNU GPLv3 license.

Copyright ©, [Olyno](https://github.com/Olyno).