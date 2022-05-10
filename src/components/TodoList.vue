<template>
    <div class="inputBox shadow">
    <input
        type="text"
        v-model="newTodoItem"
        placeholder="해야할 일을 적어주세요"
        v-on:keyup.enter="addTodo"
    />
    <span class="addContainer" v-on:click="addTodo">
        <button class="addBtn">추가</button>
    </span>

    <!-- <modal v-if="showModal" @close="showModal = false">
        <h3 slot="header">경고</h3>
        <span slot="body">할 일을 입력해주세요.</span>
        <button slot="footer" @click="showModal = false">닫기</button>
    </modal> -->
    <section>
    <transition-group name="list" tag="ul">
        <li v-for="(todoItem, index) in propsdata" v-bind:key="todoItem" class="shadow">
        <font-awesome-icon class="checkBtn" icon="check" aria-hidden="true" />
        {{ todoItem }}
        <span class="removeBtn" type="button" @click="removeTodo(todoItem, index)">
            <button class="addBtn">삭제</button>
        </span>
        </li>
    </transition-group>
    </section>
    </div>
</template>


<script>
export default {};
</script>

<style scoped>
</style>
