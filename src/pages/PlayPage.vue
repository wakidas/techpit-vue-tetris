<script lang="ts" setup>
  // フィールドを定義するコード
  const row = 20;
  const column =10;

  const field = new Array(row);

  for (let i = 0; i < row; i++){
    const fieldColumn = new Array(column).fill(0)
    field[i] = fieldColumn
  }

  field[0][0] = 1
  field[1][0] = 1
  field[2][0] = 1
  field[3][0] = 1

</script>

<template>
  <h1>プレイ画面</h1>
  <h2>ユーザー名: {{ $route.query.name }}</h2>

  <div class="container">
    <table
      class="field"
      style="border-collapse: collapse"
    >
      <tr
        v-for="(row, y) in field"
        :key="y"
      >
        <td
          v-for="(col, x) in row"
          :key="()=>`${x}${y}`"
          class="block"
        >
          {{ col }}
        </td>
      </tr>
    </table>
  </div>
</template>

<style scoped>
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .field {
    border: ridge 0.4em #2c3e50;
    border-top: none;
  }

  .block {
    width: 1em;
    height: 1em;
    border: 0.1px solid #95a5a6;
  }
</style>

