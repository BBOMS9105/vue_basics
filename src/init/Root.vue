<script>
export default {
    data() {
        return {
            message: 'Hello Vue!',
            messageHTML: '<h1>Hello, Vue with messageHTML!</h1>',
            google: 'https://www.google.com/',
            className: "color_red",
            boolean: true,
            num: 10,
            type: 'red',
            arr: ['apple', 'banana', 'orange'],
            arrInObj: [
                { id: 1, name: 'apple' },
                { id: 2, name: 'banana' },
                { id: 3, name: 'orange' },]
        };
    },
};
</script>
<template>
    <!-- mustache -->
    <h1>{{ message }}</h1>
    <h1>{{ messageHTML }}</h1>

    <!-- v-html directive -->
    <div v-html="messageHTML"></div>

    <!-- v-text directive -->
    <div v-text="message"></div>
    <div v-text="messageHTML"></div>

    <!-- v-bind directive -->
    <a href="https://vuejs.org/" target="_blank">Vue.js</a>
    <!-- v-bind => : 로 단축하여 사용할 수 있다 -->
    <!-- <a v-bind="{ href: google, target: '_blank' }" v-bind:class="className">Google</a> -->
    <a :="{ href: google, target: '_blank' }" :class="className">Google</a>

    <!-- v-pre -->
    <!-- 컴파일러가 데이터를 바인딩하지 않게(예외처리) 만든다 -->
    <div v-pre>{{ message }}</div>

    <!-- v-show -->
    <!-- 디렉티브에 바인딩 되는 값의 true와 false 여부에 따라서
         템플릿 태그 영역에 사용된 HTML 요소를 보이거나 숨김 
         dom을 숨김-->
    <div v-show="num === 10" class="box red-box"></div>
    <div class="box blue-box"></div>

    <!-- v-if -->
    <!-- 디렉티브에 바인딩 되는 값의 true와 false 여부에 따라서
         템플릿 태그 영역에 사용된 HTML 요소를 보이거나 숨김
         dom이 사라짐 -->
    <h2>v-if</h2>
    <div v-if="num - 2 === 8" class="box red-box"></div>
    <div class="box blue-box"></div>

    <!-- v-else, v-else-if -->
    <h2>v-else, v-else-if</h2>
    <div v-if="type === 'red'" class="box red-box"></div>
    <div v-else-if="type === 'blue'" class="box blue-box"></div>
    <div v-else-if="type === 'green'" class="box green-box"></div>
    <div v-else class="box yellow-box"></div>

    <!-- v-for -->
    <!-- 데이터를 기반으로 템플릿 태그 영역에
         HTML 요소를 여러 번 반복하게 하는 기능을 하는 디렉티브 -->
    <!-- <h2>v-for</h2>
    <ul>
        <li v-for="(item, index) in arr" v-bind:key="index">
            {{ index }} - {{ item }}
        </li>
    </ul> -->
    <ul>
        <li v-for="item in arr" :key="index.id">
            {{ item }}
        </li>
    </ul>
    
    
</template>
<style>
h1 {
    color: green;
}

.color_red {
    color: red;
}

.box {
    width: 100px;
    height: 100px;
    margin: 10px;
}   

.red-box {
    background-color: red;
}

.blue-box {
    background-color: blue;
}   

.green-box {
    background-color: green;
}

.yellow-box {
    background-color: yellow;
}
</style>