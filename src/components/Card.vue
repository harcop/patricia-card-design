<template>
  <div>
      <div style="display:flex; justify-content: center">
          <!-- card design -->
          <div class="card card-flex">
              <div class="inner-c">
                  <!-- layer 1 -->
                  <div class="layer1 layer">
                      <div>
                          <!-- patricia logo -->
                          <img src="../assets/patricia-logo.png" width="100px">
                      </div>
                      <div>
                          <!-- eye toggle -->
                          <span @click="toggleVisibility()" class="icon material-icons text-c3">{{icon}}</span>
                      </div>
                  </div>
                  <!-- layer 2 -->
                  <div class="layer layer2">
                      <div v-for="n in 3" :key="n">
                          <input disabled size="4" :type="visibility ? 'text' : 'password'" value="9784">
                      </div>
                      <div>
                          <input disabled size="4" type="text" value="9784">
                      </div>
                  </div>
                  <!-- layer 3 -->
                  <div class="layer layer3">
                      <div>
                          <span class="text-c1">BAMIDELE TOLUWAP</span>
                      </div>
                      <div class="layer">
                          <!-- valid thru -->
                          <div class="text-c2" style="line-height: 1; margin-right: 10px">
                              <div class="text-small">VALID</div>
                              <div class="text-small">THRU</div>
                          </div>
                          <!-- exp date -->
                          <div class="text-c1" style="margin-right: 20px">
                              <span>10/12</span>
                          </div>
                          <!-- cvv -->
                          <div>
                              <span class="text-c2">cvv</span>
                          </div>
                          <div>
                                <input disabled class="cvv-pin" :type="visibility ? 'text' : 'password'" value="455" />
                          </div>
                      </div>
                  </div>
              </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Card',
    data() {
        return {
            visibility: false,
            icon: 'visibility_off'
        }
    },
    methods: {
        toggleVisibility() {
            this.visibility = !this.visibility;
            this.icon = this.visibility ? 'visibility' : 'visibility_off';
        }
    }
}
</script>

<style>
*{
    box-sizing: border-box;
    font-family: 'Graphik', sans-serif;
    font-size: 1rem
}
.text-small {
    font-size: 10px;
}
@media(max-width: 450px) {
    * {
        font-size: 0.9rem
    }
}
.card {
    background: url('../assets/patricia-bg.png') no-repeat;
    background-size: contain;
    background-color: var(--darkg) ;
    border-radius: 20px;
    width:499px; 
    height: 305px;
}
.inner-c {
    padding: 30px 30px 10px 30px;
    height: 100%;
    display: grid;
    align-content: space-between;
}
.layer {
    display: flex;
    justify-content: space-between;
}
input {
    color: white;
    background: transparent;
    border: none;
    font-size: 20px;
}

:root {
    --darkg: #131313;
    --grey1: #d3dce6;
    --grey2: #9da8b6;
    --grey3: #575a65;
}
.text-c1 {
    color: var(--grey1);
}
.text-c2 {
    color: var(--grey2);
}
.text-c3 {
    color: var(--grey3);
}
.icon {
    cursor: pointer;
}
.cvv-pin {
    width: 4ch;
    font-size: 16px;
    text-align: end;
}
</style>