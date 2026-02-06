<script setup></script>

<script>
export default{
  name: 'App',
  data() {
	return {
    text1: '111',
		text2: '222',
		name: 'john',
		surn: 'smit',
    text: 'page',
		href: 'page.html',
    num: 5,
    num1: 1,
		num2: 2,
		num3: 3,
    arr: ['x', 'y', 'z'],
    rew: [1, 2, 3],
    obj: { x: 1, y: 2, z: 3 },
    text: 'hello',
    cost: 10,
    amount: 3
	}
},
methods: {
  showDate() {
    alert(new Date())
  },
  showSum() {
    alert(this.num1 + this.num2)
  },
  getDayName(num) {
    const days = [
      'Sunday',
      'Monday',
      'Tuesday',
      'Wednesday',
      'Thursday',
      'Friday',
      'Saturday'
    ]

    return days[num]
  },
  showToday() {
    const todayNum = new Date().getDay() // 0 - 6
    const dayName = this.getDayName(todayNum)

    alert(dayName)
  },
  showSquare(num) {
    alert(num * num)
  },
  change() {
    this.text = 'bye'
  },
  setOne() {
    this.text = 'one'
  },
  setTwo() {
    this.text = 'two'
  },
  changeCost() {
    this.cost = 20
  },
  handleClick() {
    alert('Клик по ссылке, но переход отменён')
  },
  handleOnce() {
    alert('Этот alert появится только один раз')
  }
},
computed: {
  price() {
    return this.cost * this.amount
  }
}
}
</script>
<template>
  <div> Hello world</div>
  <p>{{ text1 }}</p>
	<p>{{ text2 }}</p>
  {{ name }}
	{{ surn }}
  <p> <a href="page.html">page</a></p>
  <p>{{ num * num }}</p>
  <p>{{ num1 + num2 + num3 }}</p>
  <p>{{ arr[0] }}</p>
  <p>{{ arr[1] }}</p>
  <p>{{ arr[2] }}</p>
  <p>{{ rew[0] + rew[1] + rew[2] }}</p>
  <p>{{ obj.x + obj.y + obj.z }}</p>
	<p>{{ showDate() }}</p>
  <button @click="showDate">Показать дату</button>
  <button @mouseover="showDate">Наведи мышь</button>
  <p>{{ showSum() }}</p>
  <button @click="showToday">Показать день недели</button>
  <button @click="showSquare(2)">Квадрат 2</button>
  <button @click="showSquare(3)">Квадрат 3</button>
  <p>{{ text }}</p>
  <p>{{ text }}</p>
  <button @click="change">Изменить</button>
  <p>{{ text }}</p>
  <button @click="setOne">Установить one</button>
  <button @click="setTwo">Установить two</button>
  <p>Цена: {{ cost }}</p>
  <p>Количество: {{ amount }}</p>
  <p>Итого: {{ price }}</p>

  <button @click="changeCost">Изменить цену</button>
  <a href="https://example.com" @click.prevent="handleClick"> Link </a>
  <button @click.once="handleOnce">Click me once</button>
</template>

<style scoped></style>
