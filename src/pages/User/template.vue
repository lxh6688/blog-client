<template>
  <div id="user">
    <section class="user-info">
      <img :src="user.avatar" :alt="user.username" class="avatar">
      <h3>{{user.username}}</h3>
    </section>
    <section>
      <router-link v-for="blog in blogs" :key="blog.id" :to="`/deatail/${blog.id}`" class="item">
        <div class="date">
          <span class="day">{{splitDate(blog.createAt).date}}</span>
          <span class="month">{{splitDate(blog.createAt).month}}</span>
          <span class="year">{{splitDate(blog.createAt).year}}</span>
        </div>
        <h3>{{blog.title}}</h3>
        <p>{{blog.description}}</p>
      </router-link>
    </section>
    <section class="pagination">
      <el-pagination
       layout="prev, pager, next" 
       :total="total"
       @current-change="onPageChange"></el-pagination>
    </section>
  </div>
</template>

<script src="./template.js"></script>

<style src="../My/template.less" lang="less"></style>
