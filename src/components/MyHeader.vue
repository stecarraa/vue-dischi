  <template>
    <div>
      <div class="container-fluid ms-bg-grey"> 
      <div class="row">
    <div class="col-12 d-flex p-3 justify-content-between">
      <img src="https://cdn1.iconfinder.com/data/icons/artcorepart-4/512/spotify.png" alt="">

  <div><div class="input-group rounded">
    <input type="search" class="form-control rounded" placeholder="Search" aria-label="Search" aria-describedby="search-addon" />
    <!-- <span class="input-group-text border-0" id="search-addon">
      <i class="fas fa-search"></i>
    </span> -->
  </div>
  </div>

    </div>
      </div>
      </div>
    </div>
  </template>

  <script>
  export default {
  name:'MyHeader'
  }
  </script>

  <style lang="scss" scoped>
  img{
    height: 40px;
    
  }

  .ms-bg-grey{
    background-color: #2D3945
  }
  </style>