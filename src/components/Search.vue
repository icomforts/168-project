<template>
  <div class="searchArea">
    <h2>搜尋電影</h2>
    <form class="form" @submit.prevent="search">
      <Row type="flex" justify="center" align="middle">
        <Col span="5" class="first">
          <div class="item">
            <Input v-model="keyword" placeholder="電影名稱"></Input>
          </div>
        </Col>
        <!-- <Col span="5" class="center">
          <FormItem class="item">
            <Select
              v-model="formItem.type"
              multiple
              placeholder="選擇類型"
              :max-tag-count="2"
            >
              <Option value="beijing">New York</Option>
              <Option value="shanghai">London</Option>
              <Option value="shenzhen">Sydnsey</Option>
              <Option value="shenzhden">Sydney</Option>
              <Option value="shenzehen">Sydney</Option>
              <Option value="shenzhzen">Sydney</Option>
              <Option value="shenzhsen">Sydney</Option>
              <Option value="shenzhfen">Sydney</Option>
            </Select>
          </FormItem>
        </Col> -->
        <Col span="5">
          <div class="item">
            <button type="submit" class="searchBtn" @click="search">
              SEARCH
            </button>
          </div>
        </Col>
      </Row>
    </form>
  </div>
</template>
<script>
import errorHandler from "@/utils/errorHandlerUtility";
export default {
  props: [],
  components: {},
  computed: {},
  data() {
    return {
      keyword: "",
    };
  },
  methods: {
    search() {
      // const params = {
      //   page: 1,
      //   sort_by: "popularity.desc",
      //   with_genres: "12,28",
      //   with_keywords: "黑寡婦",
      //   with_original_language: "en",
      // };
      // window.gtag("event", "click search", {
      //   event_category: "Click",
      //   event_label: "搜尋",
      // });
      if (this.keyword)this.$router.push({ path: `/search/${this.keyword}/1` });
            },
  },
};
</script>
<style lang="scss">
.searchArea {
  margin-top: 6rem;
  padding: 0 10rem;
  h2 {
    font-size: 2rem;
    letter-spacing: 0.19rem;
    text-align: center;
    margin-bottom: 1rem;
  }
  .form {
    margin-top: 3rem;
    .center {
      margin: 0 5rem;
    }
    .item {
      display: flex;
      flex-direction: column;
      align-items: center;
      .searchBtn {
        background: transparent;
        color: #babac0;
        border: solid 1px #babac0;
        padding: 0.5rem 2rem;
        letter-spacing: 0.15rem;
        transition: all ease-in-out 0.1s;
        font-weight: bolder;
        cursor: pointer;
        &:hover {
          background: #babac0;
          color: #0f1014;
        }
      }
    }
  }
}
.ivu-form-item {
  margin-bottom: unset !important;
}
.ivu-form-item-content {
  width: 100% !important;
}
.ivu-select-multiple .ivu-select-selection .ivu-select-placeholder {
  font-size: 1.25rem !important;
  letter-spacing: 0.2rem;
}
.ivu-input,
.ivu-select-selection {
  text-align: center;
  letter-spacing: 0.2rem;
  font-size: 1.25rem !important;
  background-color: transparent !important;
  border: unset !important;
  border-radius: unset !important;
  border-bottom: solid 1px #babac0 !important;
  color: #babac0 !important;
  &:focus {
    box-shadow: unset !important;
  }
}
</style>
