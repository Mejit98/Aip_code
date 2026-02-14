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
    amount: 3,
    visible: false,
    visible1: true,
    visible2: true,
    visible3: true,
    isAuth: true,
    day: 'суббота',
    age: 25,
    visible4: true,
    items: [1, 2, 3, 4, 5],
    arr: ['x', 'y', 'z'],
    users: {
      user1: '100$',
      user2: '200$',
      user3: '300$',
    },
    items1: [1, 2, 3],
    hrefs: [
      { href: '1.html', text: 'text1' },
      { href: '2.html', text: 'text2' },
      { href: '3.html', text: 'text3' },
    ],
    products: [
      { name: 'product1', price: 100, quantity: 5 },
      { name: 'product2', price: 200, quantity: 4 },
      { name: 'product3', price: 300, quantity: 3 },
    ],
    items2: ['a', 'b', 'c'],
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
  },
  show() {
    this.visible = true
  },
  hide() {
    this.visible = false
  },
  toggle1() {
    this.visible1 = !this.visible1
  },
  toggle2() {
    this.visible2 = !this.visible2
  },
  toggle3() {
    this.visible3 = !this.visible3
  },
  add() {
    this.items.push('новый элемент');
  },
  removeFirst() {
    this.items.shift();
  },
  removeLast() {
    this.items.pop();
  },
  removeSecondLast() {
    if (this.items.length >= 2) {
      this.items.splice(this.items.length - 2, 1);
    }
  },
  sortItems() {
    this.items.sort();
  },
  reverseItems() {
    this.items.reverse();
  },
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
  <p v-if="visible">Первый абзац</p>
  <p v-if="!visible">Второй абзац</p>
  <button @click="show">Показать</button>
  <p v-if="visible">Как дела</p>
  <button @click="show">Показать</button>
  <button @click="hide">Скрыть</button>
  <p v-if="visible">Хорошо</p>
  <button @click="toggle1">
  {{ visible1 ? 'Скрыть' : 'Показать' }}
  </button>
  <p v-if="visible1">Первый абзац</p>
  <button @click="toggle2">
  {{ visible2 ? 'Скрыть' : 'Показать' }}
  </button>
  <p v-if="visible2">Второй абзац</p>
  <button @click="toggle3">
  {{ visible3 ? 'Скрыть' : 'Показать' }}
  </button>
  <p v-if="visible3">Третий абзац</p>
  <p v-if="isAuth">+++</p>
	<p v-else>---</p>
  <p v-if="day === 'понедельник'">Понедельник</p>
  <p v-if="day === 'вторник'">Вторник</p>
  <p v-if="day === 'среда'">Среда</p>
  <p v-if="day === 'четверг'">Четверг</p>
  <p v-if="day === 'пятница'">Пятница</p>
  <p v-if="day === 'суббота'">Суббота</p>
  <p v-if="day === 'воскресенье'">Воскресенье</p>
  <p v-if="age < 18">подросток</p>
  <p v-else-if="age >= 18 && age <= 25">молодой человек</p>
  <p v-else>мужчина</p>
  <button @click="hide">Скрыть абзацы</button>
  <template v-if="visible4">
    <p>Первый абзац</p>
    <p>Второй абзац</p>
    <p>Третий абзац</p>
  </template>
  <button @click="toggle">Toggle</button>
  <p v-show="visible">text</p>
  <h2>Отличия v-show и v-if</h2>
    <p>
      Директива v-if полностью удаляет и заново создаёт элемент в DOM при изменении условия.
      Она уничтожает обработчики событий и дочерние компоненты.
      Если условие изначально false, элемент вообще не создаётся.
    </p>
    <p>
      Директива v-show всегда оставляет элемент в DOM и лишь переключает CSS-свойство display.
      Элемент не пересоздаётся при каждом переключении.
    </p>

    <h2>Когда использовать v-show и v-if</h2>
    <p>
      v-show лучше использовать, если элемент будет часто показываться и скрываться
      (например, меню, вкладки, модальные окна).
    </p>
    <p>
      v-if лучше использовать, если условие меняется редко или блок может вообще не понадобиться.
      В этом случае не происходит лишней отрисовки.
    </p>

    <h2>Ограничения v-show</h2>
    <p>
      Директиву v-show нельзя использовать на элементе template.
      Она также не работает вместе с v-else и v-else-if.
      Кроме того, элемент всегда создаётся при первоначальной загрузке страницы.
    </p>
  <div v-for="item in items" :key="item">{{ item }}</div>
  <div v-for="item in items" :key="item">{{ item * item }}</div>
  <ul>
    <li v-for="item in items" :key="item">{{ item }}</li>
  </ul>
  <ul>
    <li v-for="(elem, key) in arr" :key="key">{{ key }}</li>
  </ul>
  <ul>
    <li v-for="value in users" :key="value">{{ value }}</li>
  </ul>
  <ul>
    <li v-for="(value, key) in users" :key="key">{{ key }} - {{ value }}</li>
  </ul>
  <ul>
    <li v-for="(value, key, index) in users" :key="key">
      {{ key }} - {{ value }} - {{ index }}
    </li>
  </ul>
  <ul>
    <li v-for="(value, key, index) in users" :key="key">
      {{ key }} - {{ value }} - {{ index + 1 }}
    </li>
  </ul>
  <div v-for="item in items1" :key="item">
    <p>{{ item }}</p>
    <p class="divider"></p>
  </div>
  <ul>
    <template v-for="item in items1" :key="item">
      <li>{{ item }}</li>
      <li class="divider"></li>
    </template>
  </ul>
  <ul>
    <li v-for="item in hrefs" :key="item.href">
      <a :href="item.href">{{ item.text }}</a>
    </li>
  </ul>
  <table>
    <tr v-for="product in products" :key="product.name">
      <td>{{ product.name }}</td>
      <td>{{ product.price }}</td>
      <td>{{ product.quantity }}</td>
    </tr>
  </table>
  <div>
    <p v-for="num in 30" :key="num">{{ num }}</p>
  </div>
  <ul>
    <template v-for="item in items" :key="item">
      <li v-if="item > 0">{{ item }}</li>
    </template>
  </ul>
  <ul>
    <li v-for="product in products" :key="product.id">
      {{ product.name }}
    </li>
  </ul>
  <div>
    <ul>
      <li v-for="item in items2" :key="item">{{ item }}</li>
    </ul>
    <button @click="add">Добавить элемент</button>
  </div>
  <button @click="removeFirst">Удалить первый</button>
  <button @click="removeLast">Удалить последний</button>
  <button @click="removeSecondLast">Удалить предпоследний</button>
  <button @click="sortItems">Сортировать</button>
  <button @click="reverseItems">Обратить порядок</button>
</template>

<style scoped></style>
