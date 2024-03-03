<template>
  <header>
    <div class="wrapper">
      
    <div class="title-wrapper">
      <h1 class="title">
        <span>跨国投资法律检索辅助系统</span>
      </h1>
    </div>

      <!-- <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav> -->

      <!-- 添加级联选择器 -->
      <div class="cascader-container">
        <el-cascader-panel v-model="value" :options="options" @change="handleCascaderChange" />
      </div>

      <!-- 添加文本条（在nav中），显示被选中的内容 -->
      <nav>
        <a v-if="selectedValue" :href="selectedValue" target="_blank">点击跳转、</a>
      </nav>

      <!-- <nav>
        <el-radio-group
          v-model="checkedNation"
          @change="handleCheckedNationChange"
        >
          <el-radio v-for="tag in nations" :key="tag" :label="tag">{{
            tag
          }}</el-radio>
        </el-radio-group>
      </nav>

      <nav>
        <el-checkbox
          v-model="checkAll"
          :indeterminate="isIndeterminate"
          @change="handleCheckAllChange"
          >全选</el-checkbox
        >
        <el-checkbox-group
          v-model="checkedItems"
          @change="handleCheckedItemsChange"
        >
          <el-checkbox v-for="tag in tags" :key="tag" :label="tag">{{
            tag
          }}</el-checkbox>
        </el-checkbox-group>
      </nav> -->

    </div>
  </header>

  <!-- <RouterView /> -->
</template>

<style scoped>
.cascader-container {
  /*   ***   */
  width: 1080px; /* 设置宽度为页面的80% */
  /* 其他样式规则 */
}

/* 可以为 el-cascader-panel 添加一些样式，以适应容器 */
.el-cascader-panel {
  /*   ***   */
  max-width: 1080px;
}

header {
  line-height: 1.5;
  max-height: 100vh;
}
.title-wrapper { display: flex; align-items: center;justify-content: center; } 
.title { font-size: 20px; margin: 0; } 
.title span { font-family: LiSu; font-size: 40px;  flex: 1; }
.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
  .title-wrapper {
    width: 100%; /* 让标题占满父容器的宽度 */
    text-align: center; /* 居中文本 */
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
}
</style>

<script lang="ts" setup>
import { RouterLink, RouterView } from 'vue-router'
import { onMounted, ref, watch } from 'vue';
import HelloWorld from './components/HelloWorld.vue'

onMounted(() => {
  document.title ='跨国投资法律检索系统';
});

// // // 多选框相关
// const checkedNation = ref()
// const nations = ['中国', '欧盟', '俄罗斯']

// const checkAll = ref(false)
// const isIndeterminate = ref(true)
// const checkedItems = ref([''])
// const tags = ref([''])
// const tags0 = ['法律', '行政法规', '司法解释', '部门规章', '行业规定']
// const tags1 = ['法规', '条例', '决定', '建议和意见', '指令指南', '条约公约', '协议协定', '判例']
// const tags2 = ['联邦宪法和宪法性法律', '联邦规范性法律文件', '各联邦主体法律', '国际条约、国际法原则和准则', '俄罗斯总统法令', '政府行政法规']


// const handleCheckedNationChange = (value: string) => {
//   console.log(value)
//   if (value == '中国') {
//     tags.value = tags0
//   }
//   else if (value == '欧盟') {
//     tags.value = tags1
//   }
//   else {
//     tags.value = tags2
//   }
// }

// const handleCheckAllChange = (val: boolean) => {
//   checkedItems.value = val ? tags.value : []
//   isIndeterminate.value = false
// }
// const handleCheckedItemsChange = (value: string[]) => {
//   const checkedCount = value.length
//   checkAll.value = checkedCount === tags.value.length
//   isIndeterminate.value = checkedCount > 0 && checkedCount < tags.value.length
// }



// // // 条目列表相关
// 声明一个value，用于级联选择器默认及更新
const value = ref([])
// 声明一个 ref 变量，用于存储级联选择器选择的值，并且绑定到 el-text 中
const selectedValue = ref('');
const selectedLabel = ref('');

// 处理 el-cascader-panel 的 change 事件
const handleCascaderChange = (value: any, selectedOptions: any) => {
  var len = value.length;
  var txt = value[len-1];
  console.log(len, txt);  // 打印内容，不过没有必要、

  // 依照级联选择器的value，改变 el-text 的内容
  if (txt) {
    window.open(txt, '_blank')
    selectedValue.value = txt;
  }
};

const options = ref([
<<<<<<< HEAD
{
=======
  {
    "value": "tip：各国分类层级（效力位阶）概览",
    "label": "tip：各国分类层级（效力位阶）概览",
    "children": [
      {
        "value": "中国1法律.2行政法规.3司法解释（目前未收录）.4部门规章（含：部门规章，部门规范性文件，部门工文件，行政许可批复）.5行业、团体规定",
        "label": "中国1法律.2行政法规.3司法解释（目前未收录）.4部门规章（含：部门规章，部门规范性文件，部门工文件，行政许可批复）.5行业、团体规定"
      },
      {
        "value": "欧盟 1.法规2.条例3.决定4.建议和意见，指令指南5.条约公约6.协议协定7.判例",
        "label": "欧盟 1.法规2.条例3.决定4.建议和意见，指令指南5.条约公约6.协议协定7.判例"
      },
      {
        "value": "俄罗斯1联邦宪法和宪法性法律2联邦规范性法律文件3各联邦主体法律4国际条约、国际法原则和准则5俄罗斯总统法令6政府行政法规",
        "label": "俄罗斯1联邦宪法和宪法性法律2联邦规范性法律文件3各联邦主体法律4国际条约、国际法原则和准则5俄罗斯总统法令6政府行政法规"
      },
      {
        "value": "美国：以内容分类为主，效力位阶难以分类（个别区分联邦、州）",
        "label": "美国：以内容分类为主，效力位阶难以分类（个别区分联邦、州）"
      }
    ]
  },
  {
    "value": "内容分类概览：",
    "label": "内容分类概览：",
    "children": [
      {
        "value": "投资法律制度",
        "label": "投资法律制度"
      },
      {
        "value": "贸易法律制度",
        "label": "贸易法律制度"
      },
      {
        "value": "公司设立法律制度",
        "label": "公司设立法律制度"
      },
      {
        "value": "税收法律制度",
        "label": "税收法律制度"
      },
      {
        "value": "劳动就业",
        "label": "劳动就业"
      },
      {
        "value": "工程承包法律制度",
        "label": "工程承包法律制度"
      },
      {
        "value": "土地法律制度",
        "label": "土地法律制度"
      },
      {
        "value": "环境保护制度",
        "label": "环境保护制度"
      },
      {
        "value": "土地法律制度：",
        "label": "土地法律制度："
      },
      {
        "value": "知识产权",
        "label": "知识产权"
      },
      {
        "value": "争议解决",
        "label": "争议解决"
      },
      {
        "value": "反垄断",
        "label": "反垄断"
      },
      {
        "value": "安全",
        "label": "安全"
      }
    ]
  },
  {
>>>>>>> 344e5ff1c3ea858fcabf6f5ae5df55c2843fa1fa
    "value": "中国：",
    "label": "中国：",
    "children": [
      {
        "value": "投资法律制度",
        "label": "投资法律制度",
        "children": [
          {
            "value": "行政法规",
            "label": "行政法规",
            "children": [
              {
<<<<<<< HEAD
                "value": "https://www.pkulaw.com/chl/af452aa9442746f4bdfb.html?way=listView",
=======
                "value": "国务院办公厅转发国家发展改革委商务部人民银行外交部关于进一步引导和规范境外投资方向指导意见的通知",
>>>>>>> 344e5ff1c3ea858fcabf6f5ae5df55c2843fa1fa
                "label": "国务院办公厅转发国家发展改革委商务部人民银行外交部关于进一步引导和规范境外投资方向指导意见的通知"
              }
            ]
          },
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/411abaaa11209afcbdfb.html?way=listView",
                "label": "企业境外投资管理办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/94384de2b5ef0606bdfb.html?way=listView",
                "label": "中央企业境外投资监督管理办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/90c0410630cb5cb1bdfb.html?way=listView",
                "label": "境外投资管理办法(2014)"
              },
              {
                "value": "https://www.pkulaw.com/chl/e53548b2d4377db5bdfb.html?way=listView",
                "label": "保险资金境外投资管理暂行办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/1bab8fe9a92fdf6cbdfb.html?way=listView",
                "label": "烟草行业企业境外投资项目管理办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/fc3ba1ef0d8180dabdfb.html?way=listView",
                "label": "国家计委关于印发《关于编制、审批境外投资项目的项目建议书和可行性研究报告的规定》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/950081cd5ea3af3dbdfb.html?way=listView",
                "label": "财政部关于印发《国有企业境外投资直派财务负责人管理办法》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/1471045d756b10f2bdfb.html?way=listView",
                "label": "国家发展改革委关于发布企业境外投资管理办法配套格式文本(2018年版)的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/99d07674e7bb450dbdfb.html?way=listView",
                "label": "国家发展改革委、商务部、人民银行等关于发布《民营企业境外投资经营行为规范》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/a499922b035e347abdfb.html?way=listView",
                "label": "财政部关于印发《国有企业境外投资财务管理办法》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/698010b62b83a303bdfb.html?way=listView",
                "label": "商务部办公厅关于境外投资备案实行无纸化管理和简化境外投资注销手续的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/6133ef981a1f09d3bdfb.html?way=listView",
                "label": "中国保监会关于调整保险资金境外投资有关政策的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/ed11fae200e9f09cbdfb.html?way=listView",
                "label": "商务部办公厅关于做好境外投资管理工作的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/b3cade3633f852eebdfb.html?way=listView",
                "label": "交通运输部办公厅关于鼓励和引导水运行业民营企业境外投资和跨国经营的若干意见"
              },
              {
                "value": "https://www.pkulaw.com/chl/6aa765ebce6b4c8dbdfb.html?way=listView",
                "label": "商务部办公厅关于涉及多国利益境外投资有关事项的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/05041cde7429c62bbdfb.html?way=listView",
                "label": "财政部关于规范国有企业境外投资中个人代持股份有关问题的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/580bbf5b30bca974bdfb.html?way=listView",
                "label": "商务部、国家外汇管理局关于境外投资联合年检工作有关事项的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/5b03b07fd0177c9dbdfb.html?way=listView",
                "label": "中国保险监督管理委员会关于中国财产再保险股份有限公司境外投资备案的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/b483badf24e74a61bdfb.html?way=listView",
                "label": "财政部关于印发《中央国有资本经营预算境外投资资金管理暂行办法》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/3fcbb231c672238ebdfb.html?way=listView",
                "label": "商务部办公厅、住房和城乡建设部办公厅、国家安全生产监管总局办公厅关于进一步加强境外投资合作项目安全生产工作的紧急通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/d1c12b5069784f52bdfb.html?way=listView",
                "label": "商务部关于做好境外投资管理工作有关事项的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/f1d6256c46b4c59cbdfb.html?way=listView",
                "label": "商务部办公厅关于启用“境外投资管理系统”和《企业境外投资证书》、《企业境外机构证书》等有关事项的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/e5571225c13274abbdfb.html?way=listView",
                "label": "商务部办公厅关于调整境外投资核准有关事项的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/bc95fcc989382bc0bdfb.html?way=listView",
                "label": "中国银监会办公厅关于进一步调整商业银行代客境外理财业务境外投资有关规定的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/f470661508150933bdfb.html?way=listView",
                "label": "中国银监会办公厅关于调整信托公司受托境外理财业务境外投资范围的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/63a16ba160f62a42bdfb.html?way=listView",
                "label": "中国银监会办公厅关于调整商业银行代客境外理财业务境外投资范围的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/d28115707edb6e32bdfb.html?way=listView",
                "label": "国家发展和改革委员会、商务部、外交部等关于印发《境外投资产业指导政策》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/dae4a5ded33ff03bbdfb.html?way=listView",
                "label": "全国社会保障基金境外投资管理暂行规定"
              },
              {
                "value": "https://www.pkulaw.com/chl/cf936ed51416af9bbdfb.html?way=listView",
                "label": "商务部关于印发《境外投资开办企业核准工作细则》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/3001636d0b560f49bdfb.html?way=listView",
                "label": "国家发展和改革委员会、国家开发银行关于进一步加强对境外投资重点项目融资支持有关问题的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/c689c219c5bba903bdfb.html?way=listView",
                "label": "国家发展和改革委员会、中国出口信用保险公司关于建立境外投资重点项目风险保障机制有关问题的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/1734b31d2b850c00bdfb.html?way=listView",
                "label": "国家发展改革委、中国进出口银行关于对国家鼓励的境外投资重点项目给予信贷支持政策的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/63f86be3c2ba5f62bdfb.html?way=listView",
                "label": "商务部关于做好境外投资审批试点工作有关问题的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/c8cdd04ba1f90589bdfb.html?way=listView",
                "label": "外经贸部关于印发《境外投资综合绩效评价办法(试行)》的通知"
              },
              {
                "value": "“https://www.pkulaw.com/chl/ceec067f472e6178bdfb.html?way=listView",
                "label": "“十二五”利用外资和境外投资规划"
              },
              {
                "value": "https://www.pkulaw.com/chl/cc691e1d0fe7a701bdfb.html?way=listView",
                "label": "国家发展改革委、外交部、工业和信息化部等关于印发鼓励和引导民营企业积极开展境外投资的实施意见的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/b60503ec790c4895bdfb.html?way=listView",
                "label": "商务部办公厅关于启用《中国企业境外投资批准证书》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/f3570a64687797d6bdfb.html?way=listView",
                "label": "商务部办公厅关于启用《中华人民共和国境外投资批准证书》的通知"
              },
              {
                "value": "“https://www.pkulaw.com/chl/c8aba8e447613eaabdfb.html?way=listView",
                "label": "“十五”利用外资和境外投资规划"
              },
              {
                "value": "https://www.pkulaw.com/chl/56ef74a1533b7d75bdfb.html?way=listView",
                "label": "中国银保监会关于允许境外投资者来华经营保险代理业务的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/5c19379a1e83f936bdfb.html?way=listView",
                "label": "中国银保监会关于允许境外投资者来华经营保险公估业务的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/e8880c886de2296bbdfb.html?way=listView",
                "label": "中国人民银行关于境外投资者投资境内金融机构人民币结算有关事项的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/4701c7750de88098bdfb.html?way=listView",
                "label": "国家发展改革委办公厅关于外商投资项目和境外投资项目核准有关问题的复函"
              },
              {
                "value": "https://www.pkulaw.com/chl/455a37b630f85bc5bdfb.html?way=listView",
                "label": "国家发展和改革委员会办公厅关于启用全国境外投资项目备案管理网络系统的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/0dafee64dc193652bdfb.html?way=listView",
                "label": "国家税务总局关于扩大境外投资者以分配利润直接投资暂不征收预提所得税政策适用范围有关问题的公告"
              },
              {
                "value": "https://www.pkulaw.com/chl/f53a65645ad20d3dbdfb.html?way=listView",
                "label": "财政部、税务总局、国家发展改革委、商务部关于扩大境外投资者以分配利润直接投资暂不征收预提所得税政策适用范围的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/eb732d0d3606c4c9bdfb.html?way=listView",
                "label": "国家发展改革委利用外资和境外投资司关于不再办理《符合国家产业政策的外商投资项目确认书》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/50101a27cfa3f9a6bdfb.html?way=listView",
                "label": "中国人民银行关于境外投资者因经营受让不良债权开立人民币银行结算账户有关问题的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/6cd4f8cb38911e34bdfb.html?way=listView",
                "label": "财政部关于贯彻落实《国务院关于暂停收购境外企业和进一步加强境外投资管理的通知》的紧急通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/a8e03038a132c26ebdfb.html?way=listView",
                "label": "中国人民银行上海总部公告(2017)第1号——关于中国人民银行上海总部制定了《“债券通“北向通境外投资者准入备案业务指引》的公告"
              }
            ]
          }
        ]
      },
      {
        "value": "贸易法律制度",
        "label": "贸易法律制度",
        "children": [
          {
            "value": "法律",
            "label": "法律",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/16582666334bc987bdfb.html?way=listView",
                "label": "中央人民政府委员会关于批准海关与对外贸易管理机关实行合并的决议"
              },
              {
                "value": "https://www.pkulaw.com/chl/4719179c90182f57bdfb.html?way=listView",
                "label": "中华人民共和国对外贸易法(2022修正)"
              }
            ]
          },
          {
            "value": "行政法规",
            "label": "行政法规",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/51bdd255b34ad5ebbdfb.html?way=listView",
                "label": "国务院关于“十四五”对外贸易高质量发展规划的批复"
              },
              {
                "value": "https://www.pkulaw.com/chl/bab1cec514547116bdfb.html?way=listView",
                "label": "国务院办公厅关于推进对外贸易创新发展的实施意见"
              },
              {
                "value": "https://www.pkulaw.com/chl/73526ece0d281581bdfb.html?way=listView",
                "label": "国务院关于加强进口促进对外贸易平衡发展的指导意见"
              },
              {
                "value": "https://www.pkulaw.com/chl/b3d36c47189c03f3bdfb.html?way=listView",
                "label": "国务院办公厅关于印发对外贸易经济合作部职能配置内设机构和人员编制规定的通知(1998)"
              },
              {
                "value": "https://www.pkulaw.com/chl/6d915052c5006eabbdfb.html?way=listView",
                "label": "国务院关于设立中央对外贸易发展基金有关问题的批复"
              },
              {
                "value": "https://www.pkulaw.com/chl/9b372047a654da04bdfb.html?way=listView",
                "label": "国务院办公厅关于印发对外贸易经济合作部、国家进出口商品检验局职能配置、内设机构和人员编制方案的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/a31ae30136263374bdfb.html?way=listView",
                "label": "国务院关于进一步改革和完善对外贸易体制若干问题的决定"
              },
              {
                "value": "https://www.pkulaw.com/chl/76adea22271f1bbdbdfb.html?way=listView",
                "label": "国务院关于同意向关税和贸易总协定递交《中国对外贸易制度备忘录》的批复"
              }
            ]
          },
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/e26e6cc72dc86e3dbdfb.html?way=listView",
                "label": "对外贸易经营者备案登记办法(2021修订)"
              },
              {
                "value": "https://www.pkulaw.com/chl/a36dca8531ccd74fbdfb.html?way=listView",
                "label": "对外贸易经营者违法违规行为公告办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/48242f12e02de8a2bdfb.html?way=listView",
                "label": "对外贸易经济合作部关于保障措施产品范围调整程序的暂行规则"
              },
              {
                "value": "https://www.pkulaw.com/chl/42eaddcc3f00c92abdfb.html?way=listView",
                "label": "对外贸易经济合作部关于反倾销产品范围调整程序的暂行规则"
              },
              {
                "value": "https://www.pkulaw.com/chl/0cdded0ff7506292bdfb.html?way=listView",
                "label": "外经贸部第四批废止的部门规章目录（中华人民共和国对外贸易经济合作部令2002年第24号）"
              },
              {
                "value": "https://www.pkulaw.com/chl/1c1bfab2072f7fd1bdfb.html?way=listView",
                "label": "对外贸易经济合作部、海关总署关于对走私、违规企业给予警告或暂停、撤销对外贸易、国际货运代理经营许可行政处罚的规定"
              },
              {
                "value": "https://www.pkulaw.com/chl/7c7c3130911db933bdfb.html?way=listView",
                "label": "中华人民共和国对外贸易经济合作部保障措施调查听证会暂行规则"
              },
              {
                "value": "https://www.pkulaw.com/chl/a579f540985ba769bdfb.html?way=listView",
                "label": "外经贸部第二批废止部门规章目录(中华人民共和国对外贸易经济合作部令2001年第30号)"
              },
              {
                "value": "https://www.pkulaw.com/chl/5f1dc31dd738e00abdfb.html?way=listView",
                "label": "对外贸易经济合作部和国家工商行政管理总局关于修改《关于外商投资企业合并与分立的规定》的决定"
              },
              {
                "value": "https://www.pkulaw.com/chl/2498357f45320435bdfb.html?way=listView",
                "label": "外经贸部第一批废止部门规章目录（中华人民共和国对外贸易经济合作部令２００１年第１３号）"
              },
              {
                "value": "https://www.pkulaw.com/chl/fbd73cb9354301debdfb.html?way=listView",
                "label": "对外贸易经济合作部关于印发《出口考核暂行办法》的通知"
              }
            ]
          }
        ]
      },
      {
        "value": "公司设立法律制度",
        "label": "公司设立法律制度",
        "children": [
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/4519fe1b7ccaafecbdfb.html?way=listView",
                "label": "证券公司和证券投资基金管理公司境外设立、收购、参股经营机构管理办法(2021修正)"
              },
              {
                "value": "https://www.pkulaw.com/chl/7e018b06bf2c1140bdfb.html?way=listView",
                "label": "保险公司设立境外保险类机构管理办法(2015修订)"
              },
              {
                "value": "https://www.pkulaw.com/chl/5a83fab15cd33cc1bdfb.html?way=listView",
                "label": "对外贸易经济合作部关于印发《关于设立境外贸易公司和贸易代表处的暂行规定》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/f3e69ab99a004c95bdfb.html?way=listView",
                "label": "【行政许可事项服务指南】证券公司在境外设立、收购或者参股证券经营机构审批"
              },
              {
                "value": "https://www.pkulaw.com/chl/bcc54142e7d00ca5bdfb.html?way=listView",
                "label": "中国证券监督管理委员会公告〔2017〕7号—关于取消期货公司设立、收购、参股境外期货类经营机构行政审批事项的决定"
              }
            ]
          },
          {
            "value": "行业规定",
            "label": "行业规定",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/0065d2eb59c0dfd3bdfb.html?way=listView",
                "label": "中国证券业协会关于举办证券公司境外设立、收购、参股经营机构管理办法培训班的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/443bf1db56c65399bdfb.html?way=listView",
                "label": "中国人民保险(集团)公司关于分公司不得在境外设立机构的通知"
              }
            ]
          }
        ]
      },
      {
        "value": "工程承包法律制度",
        "label": "工程承包法律制度",
        "children": [
          {
            "value": "行政法规",
            "label": "行政法规",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/6e373136b58465debdfb.html?keyword=%E5%AF%B9%E5%A4%96%E6%89%BF%E5%8C%85%E5%B7%A5%E7%A8%8B&way=listView",
                "label": "对外承包工程管理条例(2017修订)"
              },
              {
                "value": "https://www.pkulaw.com/chl/3bf503ee898129abbdfb.html?keyword=%E5%AF%B9%E5%A4%96%E6%89%BF%E5%8C%85%E5%B7%A5%E7%A8%8B&way=listView",
                "label": "国务院办公厅转发外经贸部等部门关于大力发展对外承包工程意见的通知"
              }
            ]
          },
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/711adf0f500c7493bdfb.html?way=listView",
                "label": "商务部关于印发《对外承包工程业务统计调查制度》和《对外劳务合作业务统计调查制度》的通知(2021修订)"
              },
              {
                "value": "https://www.pkulaw.com/chl/5249f18c66b66b31bdfb.html?way=listView",
                "label": "商务部、外交部、发展改革委等关于促进对外承包工程高质量发展的指导意见"
              },
              {
                "value": "https://www.pkulaw.com/chl/33dcd1ccea6aa3c3bdfb.html?way=listView",
                "label": "商务部办公厅关于请继续做好对外承包工程领域应对新冠肺炎疫情有关工作的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/cf7b648e36cf402dbdfb.html?way=listView",
                "label": "商务部办公厅、海关总署办公厅、质检总局办公厅关于做好对外承包工程资格审批取消后有关政策衔接工作的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/6c7e06f7bf682745bdfb.html?way=listView",
                "label": "商务部关于印发《对外承包工程行业社会责任指引》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/90df78819c113c68bdfb.html?way=listView",
                "label": "商务部关于做好《对外承包工程资格证书》到期换领有关工作的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/38b158b4ed2b25e4bdfb.html?way=listView",
                "label": "商务部、住房城乡建设部、安全监管总局关于印发《对外承包工程违法违规行为行政处罚规定》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/7499f166675e56b0bdfb.html?way=listView",
                "label": "财政部办公厅、商务部办公厅关于在有关国家开展对外承包工程保函风险专项资金试点工作的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/68d18042d12ce107bdfb.html?way=listView",
                "label": "商务部办公厅关于进一步强调对外承包工程项下外派劳务工作有关问题的紧急通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/e00c0d1a885c918ebdfb.html?way=listView",
                "label": "国家税务总局关于对外承包工程建筑幕墙所用材料登记备案问题的批复"
              },
              {
                "value": "https://www.pkulaw.com/chl/d4862597bef3a69fbdfb.html?way=listView",
                "label": "商务部关于印发进一步规范对外承包工程业务发展的规定的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/bb7bb25497f8e822bdfb.html?way=listView",
                "label": "商务部关于印发《对外承包工程项下外派劳务管理暂行办法》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/c388213693da2969bdfb.html?way=listView",
                "label": "财政部、商务部关于印发《对外承包工程保函风险专项资金管理暂行办法》补充规定的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/b6bc3747fbba9396bdfb.html?way=listView",
                "label": "对外贸易经济合作部、海关总署关于印发《关于对外承包工程项下出口设备材料的工作规程》补充规定的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/42042190b9325fdcbdfb.html?way=listView",
                "label": "对外承包工程保函风险专项资金管理暂行办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/e7e6fa9f986a04f3bdfb.html?way=listView",
                "label": "中国对外承包工程商会关于进一步做好外派海员劳务合作业务协调工作的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/2b89a4b4d952394fbdfb.html?way=listView",
                "label": "外经贸部关于利用出口信贷开展对外承包工程和成套设备出口实行资格审定有关问题的补充通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/c4f858b46a60945abdfb.html?way=listView",
                "label": "对外经济贸易部关于对外承包工程和劳务合作统计制度"
              },
              {
                "value": "https://www.pkulaw.com/chl/0dd9c55e0368e4fcbdfb.html?way=listView",
                "label": "中国人民银行、对外经济贸易部关于争取对外承包工程和劳务合作在国内保险的通知"
              }
            ]
          },
          {
            "value": "行业规定",
            "label": "行业规定",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/8f0e91343ce41c94bdfb.html?way=listView",
                "label": "中国对外承包工程和劳务合作行业规范（试行）"
              },
              {
                "value": "https://www.pkulaw.com/chl/734ee502847da307bdfb.html?way=listView",
                "label": "中国进出口银行关于印发《中国进出口银行对外承包工程项目贷款管理暂行办法》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/cb5da4033c39055cbdfb.html?way=listView",
                "label": "对外承包工程项目投（议）标协调办法实施细则"
              }
            ]
          }
        ]
      },
      {
        "value": "土地法律制度",
        "label": "土地法律制度",
        "children": [
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/4c0f1262c408268fbdfb.html?way=listView",
                "label": "国家税务总局关于外商投资企业征免土地使用税问题的批复"
              },
              {
                "value": "https://www.pkulaw.com/chl/05e34329d5067ef0bdfb.html?way=listView",
                "label": "国家税务总局关于外商投资企业租用场地缴纳土地使用费列支问题的函"
              },
              {
                "value": "https://www.pkulaw.com/chl/a82f77353a96dc53bdfb.html?way=listView",
                "label": "财政部关于外商投资企业租用场地如何缴土地使用费问题的答复"
              },
              {
                "value": "https://www.pkulaw.com/chl/028caf13a3f906e3bdfb.html?way=listView",
                "label": "国家税务局关于对外商投资企业从事土地开发和使用权有偿转让征收工商统一税和企业所得税问题的通知"
              }
            ]
          }
        ]
      },
      {
        "value": "税收法律制度",
        "label": "税收法律制度",
        "children": [
          {
            "value": "1.法律:",
            "label": "1.法律:",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/47bea5f5ea1fa83ebdfb.html?keyword=%E3%80%8A%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E4%BC%81%E4%B8%9A%E6%89%80%E5%BE%97%E7%A8%8E%E6%B3%95%E3%80%8B&way=listView",
                "label": "·《中华人民共和国企业所得税法》"
              },
              {
                "value": "https://www.pkulaw.com/chl/ca88b5ed5ce08c6cbdfb.html?keyword=%C2%B7%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E7%A8%8E%E6%94%B6%E5%BE%81%E6%94%B6%E7%AE%A1%E7%90%86%E6%B3%95%282015%E4%BF%AE%E6%AD%A3%29%29&way=listView",
                "label": "·中华人民共和国税收征收管理法(2015修正))"
              },
              {
                "value": "https://www.pkulaw.com/chl/169396bea504794abdfb.html?keyword=%E5%85%A8%E5%9B%BD%E4%BA%BA%E6%B0%91%E4%BB%A3%E8%A1%A8%E5%A4%A7%E4%BC%9A%E5%B8%B8%E5%8A%A1%E5%A7%94%E5%91%98%E4%BC%9A%E5%85%B3%E4%BA%8E%E4%BF%AE%E6%94%B9%E3%80%8A%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E6%B8%AF%E5%8F%A3%E6%B3%95%E3%80%8B%E7%AD%89%E4%B8%83%E9%83%A8%E6%B3%95%E5%BE%8B%E7%9A%84%E5%86%B3%E5%AE%9A%28%E5%90%AB%EF%BC%9A%E7%A8%8E%E6%94%B6%E5%BE%81%E6%94%B6%E7%AE%A1%E7%90%86%E6%B3%95%E3%80%81%E5%9B%BA%E4%BD%93%E5%BA%9F%E7%89%A9%E6%B1%A1%E6%9F%93%E7%8E%AF%E5%A2%83%E9%98%B2%E6%B2%BB%E6%B3%95%E3%80%81%E6%9E%AA%E6%94%AF%E7%AE%A1%E7%90%86%E6%B3%95%E3%80%81%E9%98%B2%E6%B4%AA%E6%B3%95%E3%80%81%E8%AF%81%E5%88%B8%E6%8A%95%E8%B5%84%E5%9F%BA%E9%87%91%E6%B3%95%E3%80%81%E5%9F%8E%E4%B9%A1%E8%A7%84%E5%88%92%E6%B3%95%29&way=listView",
                "label": "·全国人民代表大会常务委员会关于修改《中华人民共和国港口法》等七部法律的决定(含：税收征收管理法、固体废物污染环境防治法、枪支管理法、防洪法、证券投资基金法、城乡规划法)"
              },
              {
                "value": "https://www.pkulaw.com/chl/a629e8ca657697e7bdfb.html?keyword=%C2%B7%E5%85%A8%E5%9B%BD%E4%BA%BA%E6%B0%91%E4%BB%A3%E8%A1%A8%E5%A4%A7%E4%BC%9A%E5%B8%B8%E5%8A%A1%E5%A7%94%E5%91%98%E4%BC%9A%E5%85%B3%E4%BA%8E%E6%89%B9%E5%87%86%E3%80%8A%E5%A4%9A%E8%BE%B9%E7%A8%8E%E6%94%B6%E5%BE%81%E7%AE%A1%E4%BA%92%E5%8A%A9%E5%85%AC%E7%BA%A6%E3%80%8B%E7%9A%84%E5%86%B3%E5%AE%9A&way=listView",
                "label": "·全国人民代表大会常务委员会关于批准《多边税收征管互助公约》的决定"
              }
            ]
          },
          {
            "value": "2.行政法规",
            "label": "2.行政法规",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/7dc583d386b1f98bbdfb.html?keyword=%C2%B7%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E7%A8%8E%E6%94%B6%E5%BE%81%E6%94%B6%E7%AE%A1%E7%90%86%E6%B3%95%E5%AE%9E%E6%96%BD%E7%BB%86%E5%88%99%282016%E4%BF%AE%E8%AE%A2%29&way=listView",
                "label": "·中华人民共和国税收征收管理法实施细则(2016修订)"
              },
              {
                "value": "https://www.pkulaw.com/chl/9f0a96e24034becabdfb.html?keyword=%C2%B7%E5%A4%96%E5%9B%BD%E5%9C%A8%E5%8D%8E%E5%B8%B8%E4%BD%8F%E4%BA%BA%E5%91%98%E6%90%BA%E5%B8%A6%E8%BF%9B%E5%A2%83%E7%89%A9%E5%93%81%E8%BF%9B%E5%8F%A3%E7%A8%8E%E6%94%B6%E6%9A%82%E8%A1%8C%E8%A7%84%E5%AE%9A&way=listView",
                "label": "·外国在华常住人员携带进境物品进口税收暂行规定"
              },
              {
                "value": "·暂行条例有关问题的通知",
                "label": "·暂行条例有关问题的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/b1057908ca1c7261bdfb.html?keyword=%C2%B7%E5%9B%BD%E5%8A%A1%E9%99%A2%E5%8A%9E%E5%85%AC%E5%8E%85%E5%85%B3%E4%BA%8E1996%E5%B9%B43%E6%9C%8831%E6%97%A5%E5%89%8D%E6%89%B9%E5%87%86%E7%9A%84%E5%A4%96%E5%95%86%E6%8A%95%E8%B5%84%E4%BC%81%E4%B8%9A%E8%BF%9B%E5%8F%A3%E7%A8%8E%E6%94%B6%E6%94%BF%E7%AD%96%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                "label": "·国务院办公厅关于1996年3月31日前批准的外商投资企业进口税收政策的通知"
              }
            ]
          },
          {
            "value": "3.部门规章",
            "label": "3.部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/cb09391a21daec2dbdfb.html?keyword=%C2%B7%E8%A7%84%E5%AE%9A%E3%80%8B%E7%AD%893%E9%83%A8%E8%A7%84%E7%AB%A0%E7%9A%84%E5%86%B3%E5%AE%9A%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E8%B4%A2%E6%94%BF%E9%83%A8%E3%80%81%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E6%B5%B7%E5%85%B3%E6%80%BB%E7%BD%B2%E3%80%81%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E5%BA%9F%E6%AD%A2%E3%80%8A%E7%A7%91%E5%AD%A6%E7%A0%94%E7%A9%B6%E5%92%8C%E6%95%99%E5%AD%A6%E7%94%A8%E5%93%81%E5%85%8D%E5%BE%81%E8%BF%9B%E5%8F%A3%E7%A8%8E%E6%94%B6%E8%A7%84%E5%AE%9A%E3%80%8B%E7%AD%893%E9%83%A8%E8%A7%84%E7%AB%A0%E7%9A%84%E5%86%B3%E5%AE%9A&way=listView",
                "label": "·规定》等3部规章的决定中华人民共和国财政部、中华人民共和国海关总署、国家税务总局关于废止《科学研究和教学用品免征进口税收规定》等3部规章的决定"
              },
              {
                "value": "https://www.pkulaw.com/chl/49e3c819473c3440bdfb.html?keyword=%C2%B7%E8%B4%A2%E6%94%BF%E9%83%A8%E3%80%81%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E8%B7%A8%E5%A2%83%E7%94%B5%E5%AD%90%E5%95%86%E5%8A%A1%E9%9B%B6%E5%94%AE%E5%87%BA%E5%8F%A3%E7%A8%8E%E6%94%B6%E6%94%BF%E7%AD%96%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                "label": "·财政部、国家税务总局关于跨境电子商务零售出口税收政策的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/37833a137d8af709bdfb.html?keyword=%C2%B7%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E8%BF%9B%E5%87%BA%E5%8F%A3%E7%A8%8E%E6%94%B6%E7%AE%A1%E7%90%86%E5%8F%B8%E3%80%81%E6%B5%B7%E5%85%B3%E6%80%BB%E7%BD%B2%E7%9B%91%E7%AE%A1%E5%8F%B8%E5%85%B3%E4%BA%8E%E4%BD%BF%E7%94%A8%E6%96%B0%E7%96%86%E6%A3%89%E7%94%9F%E4%BA%A7%E5%87%BA%E5%8F%A3%E4%BA%A7%E5%93%81%E9%80%80%E7%A8%8E%E5%B7%A5%E4%BD%9C%E7%9A%84%E8%A1%A5%E5%85%85%E9%80%9A%E7%9F%A5&way=listView",
                "label": "·国家税务总局进出口税收管理司、海关总署监管司关于使用新疆棉生产出口产品退税工作的补充通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/b21bd7a346ef2a69bdfb.html?keyword=%C2%B7%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E5%81%9A%E5%A5%BD%E6%88%91%E5%9B%BD%E4%BC%81%E4%B8%9A%E5%A2%83%E5%A4%96%E6%8A%95%E8%B5%84%E7%A8%8E%E6%94%B6%E6%9C%8D%E5%8A%A1%E4%B8%8E%E7%AE%A1%E7%90%86%E5%B7%A5%E4%BD%9C%E7%9A%84%E6%84%8F%E8%A7%81&way=listView",
                "label": "·国家税务总局关于做好我国企业境外投资税收服务与管理工作的意见"
              },
              {
                "value": "https://www.pkulaw.com/chl/591cac594442c9d5bdfb.html?keyword=%C2%B7%E8%B4%A2%E6%94%BF%E9%83%A8%E3%80%81%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E5%A2%83%E5%A4%96%E6%89%80%E5%BE%97%E6%9C%89%E5%85%B3%E4%B8%AA%E4%BA%BA%E6%89%80%E5%BE%97%E7%A8%8E%E6%94%BF%E7%AD%96%E7%9A%84%E5%85%AC%E5%91%8A&way=listView",
                "label": "·财政部、税务总局关于境外所得有关个人所得税政策的公告"
              }
            ]
          },
          {
            "value": "4地方法规",
            "label": "4地方法规",
            "children": [
              {
                "value": "（1）地方规范性文件",
                "label": "（1）地方规范性文件",
                "children": [
                  {
                    "value": "https://www.pkulaw.com/lar/3d950bee3e69fac9d92c91c5cdb9e72fbdfb.html?keyword=%C2%B7%E6%B1%9F%E8%8B%8F%E7%9C%81%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E5%B1%80%E5%85%B3%E4%BA%8E%E8%BD%AC%E5%8F%91%E3%80%8A%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E5%81%9A%E5%A5%BD%E6%88%91%E5%9B%BD%E4%BC%81%E4%B8%9A%E5%A2%83%E5%A4%96%E6%8A%95%E8%B5%84%E7%A8%8E%E6%94%B6%E6%9C%8D%E5%8A%A1%E4%B8%8E%E7%AE%A1%E7%90%86%E5%B7%A5%E4%BD%9C%E7%9A%84%E6%84%8F%E8%A7%81%E3%80%8B%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                    "label": "·江苏省国家税务局关于转发《国家税务总局关于做好我国企业境外投资税收服务与管理工作的意见》的通知"
                  },
                  {
                    "value": "https://www.pkulaw.com/lar/d29f9eedd0900ab6a2bf1fdf08b44ac6bdfb.html?keyword=%C2%B7%E9%87%8D%E5%BA%86%E5%B8%82%E5%9C%B0%E6%96%B9%E7%A8%8E%E5%8A%A1%E5%B1%80%E8%BD%AC%E5%8F%91%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E5%81%9A%E5%A5%BD%E6%88%91%E5%9B%BD%E4%BC%81%E4%B8%9A%E5%A2%83%E5%A4%96%E6%8A%95%E8%B5%84%E7%A8%8E%E6%94%B6%E6%9C%8D%E5%8A%A1%E4%B8%8E%E7%AE%A1%E7%90%86%E5%B7%A5%E4%BD%9C%E7%9A%84%E6%84%8F%E8%A7%81%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                    "label": "·重庆市地方税务局转发国家税务总局关于做好我国企业境外投资税收服务与管理工作的意见的通知"
                  },
                  {
                    "value": "https://www.pkulaw.com/lar/3af0f5527cae1fcae1e0c22587167941bdfb.html?keyword=%C2%B7%E7%A6%8F%E5%BB%BA%E7%9C%81%E5%9C%B0%E6%96%B9%E7%A8%8E%E5%8A%A1%E5%B1%80%E8%BD%AC%E5%8F%91%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E5%81%9A%E5%A5%BD%E6%88%91%E5%9B%BD%E4%BC%81%E4%B8%9A%E5%A2%83%E5%A4%96%E6%8A%95%E8%B5%84%E7%A8%8E%E6%94%B6%E6%9C%8D%E5%8A%A1%E4%B8%8E%E7%AE%A1%E7%90%86%E5%B7%A5%E4%BD%9C%E7%9A%84%E6%84%8F%E8%A7%81%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                    "label": "·福建省地方税务局转发国家税务总局关于做好我国企业境外投资税收服务与管理工作的意见的通知"
                  },
                  {
                    "value": "https://www.pkulaw.com/lar/e60e0656203ac7dfff9b2f89474551c7bdfb.html?keyword=%C2%B7%E6%B9%96%E5%8C%97%E7%9C%81%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E5%B1%80%E8%BD%AC%E5%8F%91%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E5%81%9A%E5%A5%BD%E6%88%91%E5%9B%BD%E4%BC%81%E4%B8%9A%E5%A2%83%E5%A4%96%E6%8A%95%E8%B5%84%E7%A8%8E%E6%94%B6%E6%9C%8D%E5%8A%A1%E4%B8%8E%E7%AE%A1%E7%90%86%E5%B7%A5%E4%BD%9C%E7%9A%84%E6%84%8F%E8%A7%81%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                    "label": "·湖北省国家税务局转发国家税务总局关于做好我国企业境外投资税收服务与管理工作的意见的通知"
                  }
                ]
              },
              {
                "value": "（2）地方工作文件",
                "label": "（2）地方工作文件",
                "children": [
                  {
                    "value": "https://www.pkulaw.com/lar/5b3c949c0b5af2bf6dde837589aef276bdfb.html?keyword=%C2%B7%E5%9B%BD%E5%AE%B6%E7%A8%8E%E5%8A%A1%E6%80%BB%E5%B1%80%E5%A4%A9%E6%B4%A5%E5%B8%82%E7%A8%8E%E5%8A%A1%E5%B1%80%E5%85%B3%E4%BA%8E%E5%85%AC%E5%BC%80%E9%87%87%E8%B4%AD%E6%B3%95%E5%9B%BD%E7%AD%89%E5%9B%BD%E5%AE%B6%E6%8A%95%E8%B5%84%E7%A8%8E%E6%94%B6%E6%8C%87%E5%8D%97%E6%9C%8D%E5%8A%A1%E9%A1%B9%E7%9B%AE%E7%9A%84%E5%85%AC%E5%91%8A&way=listView",
                    "label": "·国家税务总局天津市税务局关于公开采购法国等国家投资税收指南服务项目的公告"
                  }
                ]
              }
            ]
          }
        ]
      },
      {
        "value": "劳动就业",
        "label": "劳动就业",
        "children": [
          {
            "value": "法律",
            "label": "法律",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/7ab5e7d605f859e6bdfb.html?keyword=%E3%80%8A%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E5%8A%B3%E5%8A%A8%E5%90%88%E5%90%8C%E6%B3%95%E3%80%8B&way=listView",
                "label": "《中华人民共和国劳动合同法》"
              }
            ]
          },
          {
            "value": "行政法规",
            "label": "行政法规",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/01ccafa3bb707f45bdfb.html?keyword=%E5%8A%B3%E5%8A%A8%E5%B0%B1%E4%B8%9A%E6%9C%8D%E5%8A%A1%E4%BC%81%E4%B8%9A%E7%AE%A1%E7%90%86%E8%A7%84%E5%AE%9A&way=listView",
                "label": "劳动就业服务企业管理规定"
              }
            ]
          },
          {
            "value": "司法解释",
            "label": "司法解释",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/30514e2804abfa9bbdfb.html?keyword=%E6%9C%80%E9%AB%98%E4%BA%BA%E6%B0%91%E6%B3%95%E9%99%A2%E5%85%B3%E4%BA%8E%E4%BA%BA%E6%B0%91%E6%B3%95%E9%99%A2%E5%AF%B9%E7%BB%8F%E5%8A%B3%E5%8A%A8%E4%BA%89%E8%AE%AE%E4%BB%B2%E8%A3%81%E8%A3%81%E5%86%B3%E7%9A%84%E7%BA%A0%E7%BA%B7%E5%87%86%E4%BA%88%E6%92%A4%E8%AF%89%E6%88%96%E9%A9%B3%E5%9B%9E%E8%B5%B7%E8%AF%89%E5%90%8E%E5%8A%B3%E5%8A%A8%E4%BA%89%E8%AE%AE%E4%BB%B2%E8%A3%81%E8%A3%81%E5%86%B3%E4%BB%8E%E4%BD%95%E6%97%B6%E8%B5%B7%E7%94%9F%E6%95%88%E7%9A%84%E8%A7%A3%E9%87%8A&way=listView",
                "label": "最高人民法院关于人民法院对经劳动争议仲裁裁决的纠纷准予撤诉或驳回起诉后劳动争议仲裁裁决从何时起生效的解释"
              }
            ]
          },
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/b7f70628c87cc9f6bdfb.html?keyword=%E5%8A%B3%E5%8A%A8%E5%B0%B1%E4%B8%9A%E6%9C%8D%E5%8A%A1%E4%BC%81%E4%B8%9A%E4%BA%A7%E6%9D%83%E7%95%8C%E5%AE%9A%E8%A7%84%E5%AE%9A&way=listView",
                "label": "劳动就业服务企业产权界定规定"
              },
              {
                "value": "https://www.pkulaw.com/chl/8f9a6e8582859f80bdfb.html?keyword=%E5%8A%B3%E5%8A%A8%E5%B0%B1%E4%B8%9A%E6%9C%8D%E5%8A%A1%E4%BC%81%E4%B8%9A%E5%AE%9E%E8%A1%8C%E8%82%A1%E4%BB%BD%E5%90%88%E4%BD%9C%E5%88%B6%E8%A7%84%E5%AE%9A&way=listView",
                "label": "劳动就业服务企业实行股份合作制规定"
              },
              {
                "value": "https://www.pkulaw.com/chl/cb153b156220c72cbdfb.html?keyword=%E8%83%BD%E6%BA%90%E9%83%A8%E5%85%B3%E4%BA%8E%E5%8D%B0%E5%8F%91%E3%80%8A%E7%94%B5%E5%8A%9B%E8%A1%8C%E4%B8%9A%E5%8A%B3%E5%8A%A8%E5%B0%B1%E4%B8%9A%E6%9C%8D%E5%8A%A1%E4%BC%81%E4%B8%9A%E7%AE%A1%E7%90%86%E5%8A%9E%E6%B3%95%E3%80%8B%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                "label": "能源部关于印发《电力行业劳动就业服务企业管理办法》的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/e1315fe64066cb55bdfb.html?keyword=%E7%94%B5%E5%8A%9B%E8%A1%8C%E4%B8%9A%E5%8A%B3%E5%8A%A8%E5%B0%B1%E4%B8%9A%E6%9C%8D%E5%8A%A1%E4%BC%81%E4%B8%9A%E7%AE%A1%E7%90%86%E5%8A%9E%E6%B3%95&way=listView",
                "label": "电力行业劳动就业服务企业管理办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/f3945dec2dd34ea9bdfb.html?keyword=%E5%8C%96%E5%AD%A6%E5%B7%A5%E4%B8%9A%E5%8A%B3%E5%8A%A8%E5%B0%B1%E4%B8%9A%E6%9C%8D%E5%8A%A1%E4%BC%81%E4%B8%9A%E7%AE%A1%E7%90%86%E5%8A%9E%E6%B3%95&way=listView",
                "label": "化学工业劳动就业服务企业管理办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/4bb56128a6f59b81bdfb.html?keyword=%E5%B9%BF%E6%92%AD%E7%94%B5%E5%BD%B1%E7%94%B5%E8%A7%86%E9%83%A8%E7%9B%B4%E5%B1%9E%E5%8D%95%E4%BD%8D%E5%8A%B3%E5%8A%A8%E5%B0%B1%E4%B8%9A%E6%9C%8D%E5%8A%A1%E4%BC%81%E4%B8%9A%E7%AE%A1%E7%90%86%E5%8A%9E%E6%B3%95&way=listView",
                "label": "广播电影电视部直属单位劳动就业服务企业管理办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/5339da315f0f3a75bdfb.html?keyword=%E9%82%AE%E7%94%B5%E9%83%A8%E9%97%A8%E5%8A%B3%E5%8A%A8%E5%B0%B1%E4%B8%9A%E6%9C%8D%E5%8A%A1%E4%BC%81%E4%B8%9A%E7%AE%A1%E7%90%86%E8%AF%95%E8%A1%8C%E5%8A%9E%E6%B3%95&way=listView",
                "label": "邮电部门劳动就业服务企业管理试行办法"
              }
            ]
          }
        ]
      },
      {
        "value": "环境保护",
        "label": "环境保护",
        "children": [
          {
            "value": "1法律",
            "label": "1法律",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/05384fe808d4a55fbdfb.html?keyword=%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E7%8E%AF%E5%A2%83%E4%BF%9D%E6%8A%A4%E7%A8%8E%E6%B3%95&way=listView",
                "label": "中华人民共和国环境保护税法"
              },
              {
                "value": "https://www.pkulaw.com/chl/f4c9a55acdaeac0fbdfb.html?keyword=%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E6%B5%B7%E6%B4%8B%E7%8E%AF%E5%A2%83%E4%BF%9D%E6%8A%A4%E6%B3%95&way=listView",
                "label": "中华人民共和国海洋环境保护法"
              }
            ]
          },
          {
            "value": "行政法规",
            "label": "行政法规",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/aeaac6abb7227ca5bdfb.html?keyword=%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E7%8E%AF%E5%A2%83%E4%BF%9D%E6%8A%A4%E7%A8%8E%E6%B3%95%E5%AE%9E%E6%96%BD%E6%9D%A1%E4%BE%8B&way=listView",
                "label": "中华人民共和国环境保护税法实施条例"
              },
              {
                "value": "https://www.pkulaw.com/chl/8d83bf01b80de0d2bdfb.html?keyword=%E5%BB%BA%E8%AE%BE%E9%A1%B9%E7%9B%AE%E7%8E%AF%E5%A2%83%E4%BF%9D%E6%8A%A4%E7%AE%A1%E7%90%86%E6%9D%A1%E4%BE%8B%282017%E4%BF%AE%E8%AE%A2%29&way=listView",
                "label": "建设项目环境保护管理条例(2017修订)"
              }
            ]
          },
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "管理规定",
                "label": "管理规定"
              },
              {
                "value": "https://www.pkulaw.com/chl/72f224f5b12a6e50bdfb.html?keyword=%E4%B8%AD%E5%A4%AE%E4%BC%81%E4%B8%9A%E8%8A%82%E7%BA%A6%E8%83%BD%E6%BA%90%E4%B8%8E%E7%94%9F%E6%80%81%E7%8E%AF%E5%A2%83%E4%BF%9D%E6%8A%A4%E7%9B%91%E7%9D%A3%E7%AE%A1%E7%90%86%E5%8A%9E%E6%B3%95&way=listView",
                "label": "中央企业节约能源与生态环境保护监督管理办法"
              }
            ]
          }
        ]
      },
      {
        "value": "知识产权",
        "label": "知识产权",
        "children": [
          {
            "value": "1法律",
            "label": "1法律",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/afbefa14a6315261bdfb.html?keyword=%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E7%9F%A5%E8%AF%86%E4%BA%A7%E6%9D%83%E6%B5%B7%E5%85%B3%E4%BF%9D%E6%8A%A4%E6%9D%A1%E4%BE%8B%282018%E4%BF%AE%E8%AE%A2%29&way=listView",
                "label": "中华人民共和国知识产权海关保护条例(2018修订)"
              }
            ]
          },
          {
            "value": "2行政法规",
            "label": "2行政法规",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/e74d8f024787903fbdfb.html?keyword=%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E6%B5%B7%E5%85%B3%E5%85%B3%E4%BA%8E%E3%80%8A%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E7%9F%A5%E8%AF%86%E4%BA%A7%E6%9D%83%E6%B5%B7%E5%85%B3%E4%BF%9D%E6%8A%A4%E6%9D%A1%E4%BE%8B%E3%80%8B%E7%9A%84%E5%AE%9E%E6%96%BD%E5%8A%9E%E6%B3%95%282018%E4%BF%AE%E6%AD%A3%29&way=listView",
                "label": "中华人民共和国海关关于《中华人民共和国知识产权海关保护条例》的实施办法(2018修正)"
              }
            ]
          },
          {
            "value": "3部门规章",
            "label": "3部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/58d509da0a9c7a7cbdfb.html?keyword=%E5%8D%AB%E7%94%9F%E7%B3%BB%E7%BB%9F%E4%BF%9D%E6%8A%A4%E6%B6%89%E5%A4%96%E7%9F%A5%E8%AF%86%E4%BA%A7%E6%9D%83%E6%9A%82%E8%A1%8C%E8%A7%84%E5%AE%9A%EF%BC%88%E8%AF%95%E8%A1%8C%EF%BC%89&way=listView",
                "label": "卫生系统保护涉外知识产权暂行规定（试行）"
              },
              {
                "value": "http://www.csres.com/notice/54240.html",
                "label": "中华人民共和国国家标准公告[2020]24号一一关于批准发布《电子商务平台知识产权保护管理》等8项国家标准的公告"
              }
            ]
          }
        ]
      },
      {
        "value": "争议解决（找国际条约）",
        "label": "争议解决（找国际条约）",
        "children": [
          {
            "value": "4地方法规",
            "label": "4地方法规",
            "children": [
              {
                "value": "地方工作文件",
                "label": "地方工作文件",
                "children": [
                  {
                    "value": "https://www.pkulaw.com/lar/316991422b916a8ead5515f55757f3a8bdfb.html?keyword=%E6%9D%AD%E5%B7%9E%E5%B8%82%E5%BE%8B%E5%B8%88%E5%8D%8F%E4%BC%9A%E5%9B%BD%E9%99%85%E6%8A%95%E8%B5%84%E4%B8%93%E4%B8%9A%E5%A7%94%E5%91%98%E4%BC%9A%E5%85%B3%E4%BA%8E%E5%8F%AC%E5%BC%80%E6%B6%89%E5%A4%96%E6%8A%95%E8%B5%84%E4%BA%89%E8%AE%AE%E7%9A%84%E4%BB%B2%E8%A3%81%E8%A7%A3%E5%86%B3%E6%B3%95%E5%BE%8B%E5%AE%9E%E5%8A%A1%E8%AE%BA%E5%9D%9B%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                    "label": "杭州市律师协会国际投资专业委员会关于召开涉外投资争议的仲裁解决法律实务论坛的通知"
                  },
                  {
                    "value": "https://www.pkulaw.com/lar/b58a0bcb45af560fb992e9ec052630a2bdfb.html?keyword=%E7%A6%8F%E5%BB%BA%E7%9C%81%E5%BE%8B%E5%B8%88%E5%8D%8F%E4%BC%9A%E5%85%B3%E4%BA%8E%E4%B8%BE%E5%8A%9E%E5%9B%BD%E9%99%85%E6%8A%95%E8%B5%84%E4%BB%B2%E8%A3%81%E5%8A%A9%E5%8A%9B%E6%88%91%E5%9B%BD%E6%B5%B7%E5%A4%96%E6%8A%95%E8%B5%84%E4%BA%89%E8%AE%AE%E8%A7%A3%E5%86%B3%E4%BA%A4%E6%B5%81%E6%B4%BB%E5%8A%A8%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                    "label": "福建省律师协会关于举办国际投资仲裁助力我国海外投资争议解决交流活动的通知"
                  }
                ]
              }
            ]
          }
        ]
      },
      {
        "value": "安全法律制度",
        "label": "安全法律制度",
        "children": [
          {
            "value": "行政法规",
            "label": "行政法规",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/69c1c77a4522afe6bdfb.html?keyword=%E5%9B%BD%E5%8A%A1%E9%99%A2%E5%8A%9E%E5%85%AC%E5%8E%85%E5%85%B3%E4%BA%8E%E5%8D%B0%E5%8F%91%E8%87%AA%E7%94%B1%E8%B4%B8%E6%98%93%E8%AF%95%E9%AA%8C%E5%8C%BA%E5%A4%96%E5%95%86%E6%8A%95%E8%B5%84%E5%9B%BD%E5%AE%B6%E5%AE%89%E5%85%A8%E5%AE%A1%E6%9F%A5%E8%AF%95%E8%A1%8C%E5%8A%9E%E6%B3%95%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                "label": "国务院办公厅关于印发自由贸易试验区外商投资国家安全审查试行办法的通知"
              },
              {
                "value": "https://www.pkulaw.com/chl/0185b6e0ab7af80ebdfb.html?keyword=%E5%9B%BD%E5%8A%A1%E9%99%A2%E5%8A%9E%E5%85%AC%E5%8E%85%E5%85%B3%E4%BA%8E%E5%BB%BA%E7%AB%8B%E5%A4%96%E5%9B%BD%E6%8A%95%E8%B5%84%E8%80%85%E5%B9%B6%E8%B4%AD%E5%A2%83%E5%86%85%E4%BC%81%E4%B8%9A%E5%AE%89%E5%85%A8%E5%AE%A1%E6%9F%A5%E5%88%B6%E5%BA%A6%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                "label": "国务院办公厅关于建立外国投资者并购境内企业安全审查制度的通知"
              }
            ]
          },
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/c9e69a9f6ef98599bdfb.html?keyword=%E5%A4%96%E5%95%86%E6%8A%95%E8%B5%84%E5%AE%89%E5%85%A8%E5%AE%A1%E6%9F%A5%E5%8A%9E%E6%B3%95&way=listView",
                "label": "外商投资安全审查办法"
              },
              {
                "value": "https://www.pkulaw.com/chl/c2bbe54b375901debdfb.html?keyword=%E5%95%86%E5%8A%A1%E9%83%A8%E5%85%AC%E5%91%8A2011%E5%B9%B4%E7%AC%AC53%E5%8F%B7%E2%80%94%E5%95%86%E5%8A%A1%E9%83%A8%E5%AE%9E%E6%96%BD%E5%A4%96%E5%9B%BD%E6%8A%95%E8%B5%84%E8%80%85%E5%B9%B6%E8%B4%AD%E5%A2%83%E5%86%85%E4%BC%81%E4%B8%9A%E5%AE%89%E5%85%A8%E5%AE%A1%E6%9F%A5%E5%88%B6%E5%BA%A6%E7%9A%84%E8%A7%84%E5%AE%9A&way=listView",
                "label": "商务部公告2011年第53号—商务部实施外国投资者并购境内企业安全审查制度的规定"
              },
              {
                "value": "https://www.pkulaw.com/chl/ce0975fda14bca14bdfb.html?keyword=%E5%95%86%E5%8A%A1%E9%83%A8%E5%85%AC%E5%91%8A2011%E5%B9%B4%E7%AC%AC8%E5%8F%B7%E2%80%94%E5%85%AC%E5%B8%83%E3%80%8A%E5%95%86%E5%8A%A1%E9%83%A8%E5%AE%9E%E6%96%BD%E5%A4%96%E5%9B%BD%E6%8A%95%E8%B5%84%E8%80%85%E5%B9%B6%E8%B4%AD%E5%A2%83%E5%86%85%E4%BC%81%E4%B8%9A%E5%AE%89%E5%85%A8%E5%AE%A1%E6%9F%A5%E5%88%B6%E5%BA%A6%E6%9C%89%E5%85%B3%E4%BA%8B%E9%A1%B9%E7%9A%84%E6%9A%82%E8%A1%8C%E8%A7%84%E5%AE%9A%E3%80%8B&way=listView",
                "label": "商务部公告2011年第8号—公布《商务部实施外国投资者并购境内企业安全审查制度有关事项的暂行规定》"
              }
            ]
          }
        ]
      },
      {
        "value": "反垄断",
        "label": "反垄断",
        "children": [
          {
            "value": "法律",
            "label": "法律",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/d3236788421feacfbdfb.html?keyword=%E4%B8%AD%E5%8D%8E%E4%BA%BA%E6%B0%91%E5%85%B1%E5%92%8C%E5%9B%BD%E5%8F%8D%E5%9E%84%E6%96%AD%E6%B3%95%282022%E4%BF%AE%E6%AD%A3%29&way=listView",
                "label": "中华人民共和国反垄断法(2022修正)"
              }
            ]
          },
          {
            "value": "部门规章",
            "label": "部门规章",
            "children": [
              {
                "value": "https://www.pkulaw.com/chl/bb4268005c34457cbdfb.html?keyword=%E5%B8%82%E5%9C%BA%E7%9B%91%E7%AE%A1%E6%80%BB%E5%B1%80%E5%85%B3%E4%BA%8E%E5%8D%B0%E5%8F%91%E3%80%8A%E4%BC%81%E4%B8%9A%E5%A2%83%E5%A4%96%E5%8F%8D%E5%9E%84%E6%96%AD%E5%90%88%E8%A7%84%E6%8C%87%E5%BC%95%E3%80%8B%E7%9A%84%E9%80%9A%E7%9F%A5&way=listView",
                "label": "市场监管总局关于印发《企业境外反垄断合规指引》的通知"
              }
            ]
          }
        ]
      }
    ]
  },
  {
    "value": "欧洲",
    "label": "欧洲",
    "children": [
      {
        "value": "贸易法律制度",
        "label": "贸易法律制度",
        "children": [
          {
            "value": "进口管理法规",
            "label": "进口管理法规",
            "children": [
              {
                "value": "http://data.europa.eu/eli/reg/2019/880/oj",
                "label": "《2019 年 4 月 17 日欧洲议会和理事会关于文化产品引进和进口的第 2019/880 号法规（EU）》"
              },
              {
                "value": "http://data.europa.eu/eli/reg/2015/755/oj",
                "label": "《2015 年 4 月 29 日欧洲议会和理事会关于从某些第三国进口的共同规则的条例 （EU） 2015/755（修订）》"
              },
          {
            "value": "出口管理法规",
            "label": "出口管理法规",
            "children": [
              {
                "value": "法规",
                "label": "法规",
                "children": [
                  {
                    "value": "http://data.europa.eu/eli/reg/2021/821/oj",
                    "label": "《2021 年 5 月 20 日欧洲议会和理事会第 2021/821 号条例 （EU），该条例建立了控制两用物项出口、经纪、技术援助、过境和转让的联盟制度（重铸）》"
                  },
                  {
                    "value": "http://data.europa.eu/eli/reg/2012/258/oj",
                    "label": "《2012年3月14日欧洲议会和理事会第258/2012号条例（欧盟），其中关于执行《联合国打击跨国有组织犯罪公约关于打击非法制造和贩运枪支及其零部件和弹药的补充议定书》第10条，并确立枪支的出口许可、进口和过境措施， 其零部件和弹药》"
                  }，
          {
            "value": "贸易救济措施",
            "label": "贸易救济措施",
            "children": [
              {
                "value": "反倾销",
                "label": "反倾销",
                "children": [
                  {
                    "value": "判例",
                    "label": "判例",
                    "children": [
                      {
                        "value": "http://data.europa.eu/eli/reg_impl/2021/1483/oj",
                        "label": "2021 年 9 月 15 日欧盟委员会实施条例 （EU） 2021/1483，根据欧洲议会和理事会第 2016/1036 号条例 （EU） 第 11（2） 条进行到期审查后，对原产于中华人民共和国和台湾的进口不锈钢冷轧扁平产品征收最终反倾销税"
                      }
                    ]
                  }
                ]
              },
              {
                "value": "反补贴",
                "label": "反补贴",
                "children": [
                  {
                    "value": "判例",
                    "label": "判例",
                    "children": [
                      {
                        "value": "http://data.europa.eu/eli/reg/2008/1010/oj",
                        "label": "2008年10月13日第1010/2008号条例（EC）第1010/2008号条例，在根据第2026/97号条例（EC）第18条进行到期审查后，对原产于印度的磺酸进口征收明确的反补贴税，并根据第2026/97号条例（EC）第19条进行部分临时审查，并修订第1000/2008号条例（EC），对原产于中华人民共和国和印度的进口硫酸征收明确的反倾销税根据第 （EC） 第 384/96 号条例第 11（2） 条进行的到期审查"
                      }
                    ]
                  }
                ]
              }
            ]
          },
          {
            "value": "食品安全及动植物卫生管理",
            "label": "食品安全及动植物卫生管理",
            "children": [
              {
                "value": "法规",
                "label": "法规",
                "children": [
                  {
                    "value": "http://data.europa.eu/eli/reg/2002/178/oj",
                    "label": "《食品基本法》"
                  }
                ]
              },
              {
                "value": "条例",
                "label": "条例",
                "children": [
                  {
                    "value": "http://data.europa.eu/eli/reg/2004/852/oj",
                    "label": "欧盟理事会有关食品卫生的第852/2004号条例"
                  },
                  {
                    "value": "http://data.europa.eu/eli/reg/2004/853/oj",
                    "label": "有关动物源性食品特殊卫生规则的第853/2004号条例"
                  },
                ]
              }
            ]
          },
          {
            "value": "共同海关税则",
            "label": "共同海关税则",
            "children": [
              {
                "value": "条例",
                "label": "条例",
                "children": [
                  {
                    "value": "http://data.europa.eu/eli/reg/1987/2658/oj",
                    "label": "欧盟理事会第2658/87号条例"
                  }
                ]
              }
            ]
          }
        ]
      },
      {
        "value": "争议解决法律制度--投资法庭制度",
        "label": "争议解决法律制度--投资法庭制度",
        "children": [
          {
            "value": "条约",
            "label": "条约",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/EN/legal-content/summary/the-treaty-of-lisbon.html",
                "label": "里斯本条约"
              }
            ]
          },
          {
            "value": "协定",
            "label": "协定",
            "children": [
              {
                "value": "欧盟与各国签订的投资贸易协定",
                "label": "欧盟与各国签订的投资贸易协定"
              }
            ]
          }
        ]
      },
      {
        "value": "反垄断法律制度",
        "label": "反垄断法律制度",
        "children": [
          {
            "value": "反垄断法律法规",
            "label": "反垄断法律法规",
            "children": [
              {
                "value": "条例",
                "label": "条例",
                "children": [
                  {
                    "value": "https://eur-lex.europa.eu/EN/legal-content/summary/treaty-of-rome-eec.html",
                    "label": "《欧洲经济共同体条约》81/82条"
                  },
                  {
                    "value": "http://www.euchinacomp.org/attachments/article/46/02_Council_Regulation_EC_No_1_2003_CN.pdf",
                    "label": "《第十七号理事会条例》"
                  },
                  {
                    "value": "http://data.europa.eu/eli/reg/2003/1/oj",
                    "label": "《第1/2003号理事会条例》（2002）"
                  },
                  {
                    "value": "https://eur-lex.europa.eu/EN/legal-content/summary/treaty-on-the-functioning-of-the-european-union.html",
                    "label": "《欧盟运行条约》101/102条（2019）"
                  }
                ]
              }
            ]
          },
          {
            "value": "数字市场反垄断规制",
            "label": "数字市场反垄断规制",
            "children": [
              {
                "value": "法规",
                "label": "法规",
                "children": [
                  {
                    "value": "http://data.europa.eu/eli/reg/2022/1925/oj",
                    "label": "《数字市场法》（2020）"
                  },
                  {
                    "value": "http://data.europa.eu/eli/reg/2022/2065/oj",
                    "label": "《数字服务法》（2020）"
                  }
                ]
              },
              {
                "value": "条例",
                "label": "条例",
                "children": [
                  {
                    "value": "http://data.europa.eu/eli/reg/2016/679/oj",
                    "label": "《一般数据保护条例》（2018）"
                  }
                ]
              },
              {
                "value": "指南建议",
                "label": "指南建议",
                "children": [
                  {
                    "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/PDF/?uri=CELEX:32016R0679",
                    "label": "《关于2016/679号条例第46 (2) (a) 条和第46 (3) (b) 条在欧盟和非欧盟公共机构之间个人数据传输的第02/2020号指南》"
                  },
                  {
                    "value": "http://data.europa.eu/eli/reg/2016/679/oj",
                    "label": "《关于2016/679号条例项下同意条款的第05/2020号指南》"
                  },
                  {
                    "value": "http://data.europa.eu/eli/reg/2016/679/oj",
                    "label": "《关于2016/679号条例项下的相关和合理异议的第09/2020号指南》"
                  },
                  {
                    "value": "https://edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-32019-processing-personal-data-through-video_en",
                    "label": "《关于通过视频设备处理个人数据的第03/2019号指南》"
                  },
                  {
                    "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_201904_dataprotection_by_design_and_by_default_v2.0_en.pdf",
                    "label": "《关于 (HDPR第25条的设计和默认隐私保护2.0的第04/2019号指南》《关于处理车联网有关应用中的个人数据的第01/2020号指南》"
                  },
                  {
                    "value": "https://edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-22020-articles-46-2-and-46-3-b-regulation_en",
                    "label": "《关于2016/679号条例第46 (2) (a) 条和第46 (3) (b) 条在欧盟和非欧盟公共机构之间个人数据传输的第02/2020号指南》"
                  },
                  {
                    "value": "http://data.europa.eu/eli/reg/2016/679/oj",
                    "label": "《关于 2016/679号条例项下同意条款的第05/2020号指南》"
                  },
                  {
                    "value": "https://commission.europa.eu/law/law-topic/data-protection/eu-data-protection-rules_en",
                    "label": "《关于〈支付服务指令Ⅱ〉和GDPR的协调适用关系的第06/2020号指南》"
                  },
                  {
                    "value": "https://commission.europa.eu/law/law-topic/data-protection/eu-data-protection-rules_en",
                    "label": "《关于GDPR第23条项下的限制主体权利的第10/2020号指南》"
                  },
                ]
              }
            ]
          }
        ]
      },
      {
        "value": "知识产权",
        "label": "知识产权",
        "children": [
          {
            "value": "条约",
            "label": "条约",
            "children": [
              {
                "value": "https://www.wipo.int/wipolex/zh/text/318029",
                "label": "《商标法条约》"
              },
              {
                "value": "https://www.wipo.int/wipolex/zh/text/322976",
                "label": "《海牙协定》"
              },
              {
                "value": "https://www.wipo.int/wipolex/zh/text/283466",
                "label": "《马德里议定书》"
              },
              {
                "value": "https://www.wipo.int/wipolex/zh/text/283696",
                "label": "《伯尔尼公约》"
              },
              {
                "value": "http://ipr.mofcom.gov.cn/zhuanti/law/conventions/wto/trips_right.html",
                "label": "《与贸易（包括假冒商品贸易在内的）有关的知识产权协定》"
              },
              {
                "value": "https://www.cpahkltd.com/UploadFiles/20110603102159616.pdf",
                "label": "《反假冒贸易协定》（ACTA）"
              },
              {
                "value": "https://www.epo.org/en/legal/epc/2020/EPC_conv_20231101_en_20231101.pdf",
                "label": "《欧洲专利公约》EPC"
              }
            ]
          },
          {
            "value": "判例",
            "label": "判例",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A62022CJ0201&qid=1709042559580",
                "label": "法院判决（第五分庭）2023年11月23日 （ *1 )（初步裁决参考 – 知识产权 – 指令 2014/26/EU – 版权及相关 权的集体管理 – 集体管理组织 – 指令 2004/48/EC – 确保知识产权执法所需的措施、程序和补救措施– 第 4 条 – 有权寻求适用第 2004/48/EC 号指令中规定的措施、程序和补救措施的人 – 有权进行扩展集体许可的集体管理组织 – 有权提起知识产权 辩护诉讼)"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A62021CJ0628&qid=1709042735970",
                "label": "法院（第五分庭）2023年4月27日的判决。初步裁决参考 – 知识产权 – 指令 2004/48/EC – 确保知识产权执法所需的措施、程序和补救措施 – 信息权 – 诉讼地位 – 需要事先确定知识产权的存在。案件C-628/21。"
              }
            ]
          },
          {
            "value": "指令",
            "label": "指令",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A52006PC0226&qid=1709042768099",
                "label": "欧洲议会和理事会关于知识产权领域租赁权和出借权以及与版权有关的某些权利的指令提案（编纂版）/* COM/2006/0226 final - COD 2006/0073 */"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32004L0048&qid=1709042917697",
                "label": "委员会向欧洲议会、欧洲理事会、欧洲经济和社会委员会以及地区委员会提交的报告 适用欧洲议会和理事会2004年4月29日关于知识产权执法的第2004/48/EC号指令"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A52005XC0526%2801%29&qid=1709042987734",
                "label": "第三国知识产权 执法战略（2005/C 129/03）"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A52005PC0276%2801%29&qid=1709043014054",
                "label": "关于欧洲议会和理事会关于旨在确保知识产权执法的刑事措施的指令的提案 {SEC（2005）848}"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A52021PC0183&qid=1709043045268",
                "label": "关于代表欧洲联盟在世界贸易组织与贸易有关的知识产权理事会中采取的立场的理事会决定的理事会的提案COM/2021/183 决赛"
              }
            ]
          }
        ]
      },
      {
        "value": "国家安全",
        "label": "国家安全",
        "children": [
          {
            "value": "指令",
            "label": "指令",
            "children": [
              {
                "value": "https://gdpr-info.eu/",
                "label": "《一般数据保护条例》(GDPR)《2016/680指令》《2018/1725指令》"
              }
            ]
          },
          {
            "value": "指南",
            "label": "指南",
            "children": [
              {
                "value": "https://edpb.europa.eu/system/files/2021-03/edpb_guidelines_202001_connected_vehicles_v2.0_adopted_en.pdf",
                "label": "《关于处理车联网有关应用中的个人数据的第01/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-22020-articles-46-2-and-46-3-b-regulation_en",
                "label": "《关于2016/679号条例第46 (2)(a) 条和第46 (3) (b) 条在欧盟和非欧盟公共机构之间个一人数据传输的第02/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_202003_healthdatascientificresearchcovid19_en.pdf",
                "label": "《关于新冠疫情背景下的科学研究目的处理健康数据的第03/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_20200420_contact_tracing_covid_with_annex_en.pdf",
                "label": "《关于在新冠疫情中使用位置数据和接触者追踪工具的第04/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_20200420_contact_tracing_covid_with_annex_en.pdf",
                "label": "《关于 2016/679号条例项下同意条款的第05/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/our-work-tools/our-documents/guidelines/guidelines-062020-interplay-second-payment-services_en",
                "label": "《关于〈支付服务指令II〉和GDPR的协调适用关系的第06/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/system/files/2023-10/EDPB_guidelines_202007_controllerprocessor_final_en.pdf",
                "label": "《关于GDPR 中数据控制者和数据处理者概念的第07/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/consultation/edpb_guidelines_202008_onthetargetingofsocialmediausers_en.pdf",
                "label": "《关于社交媒体用户提供定向服务的第08/2020号准则》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_202005_consent_en.pdf",
                "label": "《关于2016/679号条例项下的相关和合理异议的第09/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/system/files/2021-10/edpb_guidelines202010_on_art23_adopted_after_consultation_en.pdf",
                "label": "《关于GDPR第23条项下的限制主体权利的第10/2020号指南》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_201903_video_devices_en_0.pdf",
                "label": "《关于通过视频设备处理个人数据的第03/2019号指南》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_201905_rtbfsearchengines_afterpublicconsultation_en.pdf",
                "label": "《关于GIPK 下搜索引擎案件中被遗忘权认定标准的第05/2019号指南(第1部分) 》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_guidelines_201904_dataprotection_by_design_and_by_default_v2.0_en.pdf",
                "label": "《关于(HDPR第25条的设计和默认隐私保护2.0的第04/2019号指南》"
              }
            ]
          },
          {
            "value": "建议",
            "label": "建议",
            "children": [
              {
                "value": "https://edpb.europa.eu/system/files/2021-06/edpb_recommendations_202001vo.2.0_supplementarymeasurestransferstools_en.pdf",
                "label": "《关于采取传输T具补充措施以确保符合欧盟个人数据保护水平的第01/2020号建议》"
              },
              {
                "value": "https://edpb.europa.eu/sites/default/files/files/file1/edpb_recommendations_202002_europeanessentialguaranteessurveillance_en.pdf",
                "label": "《针对监控措施的关于欧盟重要保障的第002/2020号建议》"
              }
            ]
          }
        ]
      },
      {
        "value": "工程承包",
        "label": "工程承包",
        "children": [
          {
            "value": "法律",
            "label": "法律",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32003L0071",
                "label": "欧洲土地法典： European Code on Land Law，编号： COM(2003) 71 final"
              }
            ]
          },
          {
            "value": "判例",
            "label": "判例",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A62022CA0011&qid=1709026052792",
                "label": "2023 年 10 月 12 日法院（第一分庭）的判决（要求爱沙尼亚塔林纳哈尔杜斯科胡斯做出初步裁决）——Est Wind Power OÜ v Elering AS（案例 C-11/22，"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A62009CA0224&qid=1709026285688",
                "label": "2010年10月7日法院（第五分庭）判决（参考意大利博尔扎诺法庭的初步裁决）——对玛莎·努斯鲍默的刑事诉讼（案件编号C-224/09）"
              }
            ]
          },
          {
            "value": "● 指令",
            "label": "● 指令",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32004L0035&qid=1709041607521",
                "label": "● 欧洲土地资源保护指令：European Directive on Protection of Soil Resources，编号：2004/35/EC"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32011L0092&qid=1709041691315",
                "label": "● 关于欧盟土地使用和开发指令：European Directive onLand Use and Development，编号：2011/92/EU"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32021L1883&qid=1709041765145",
                "label": "● 欧洲议会和理事会指令 （EU） 2021/1883 关于第三国国民为高素质就业而入境和居住的条件，并废除理事会指令 2009/50/EC"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32021L1883&qid=1709041765145",
                "label": "● 欧洲议会和理事会指令 2014/54/EU   在工人行动自由的背景下，便利行使赋予工人的权利的措施（与欧洲经济区相关的文本）"
              },
              {
                "value": "● 指南",
                "label": "● 指南"
              },
              {
                "value": "https://minerva.jrc.ec.europa.eu/EN/content/minerva/a0bf56b7-79a0-454e-a84a-02b6e0a2a990/lupguideseviipdf",
                "label": "●  欧洲土地利用规划指南：European Guidelines for Land Use Planning，编号：COM(1999) 224 final"
              }
            ]
          }
        ]
      },
      {
        "value": "税收",
        "label": "税收",
        "children": [
          {
            "value": "条约",
            "label": "条约",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/eli/treaty/teec/sign",
                "label": "《欧共体条约》"
              },
              ]
          },
          {
            "value": "法律法规",
            "label": "法律法规",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32011L0016",
                "label": "税务合作指令"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=celex%3A32018L0822",
                "label": "欧洲税收透明度指令"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=celex%3A32013L0011",
                "label": "争端解决机制指令"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32006L0112",
                "label": "增值税指令"
              }
            ]
          },
          {
            "value": "条例",
            "label": "条例",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32018R1042",
                "label": "跨境交易增值税条例"
              }
            ]
          },
          {
            "value": "判例法",
            "label": "判例法",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A61991CJ0069",
                "label": "进口生产资料税抵免案（Case C-69/91）"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A62009CJ0384",
                "label": "欧元货币税（Case C-384/09）"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A62003CJ0172",
                "label": "违反国家援助规定的税收减免案（Case C-172/03）"
              }
            ]
          },
          {
            "value": "指南",
            "label": "指南",
            "children": [
               {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A12016E%2FTXT",
                "label": "内部市场和关税同盟指南"
              },
            ]
          }
        ]
      },
      {
        "value": "环境保护",
        "label": "环境保护",
        "children": [
          {
            "value": "条约",
            "label": "条约",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ%3AC%3A2016%3A202%3ATOC",
                "label": "《欧洲联盟运作条约》第191，第193条；附加议定书第二部分"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ%3AC%3A2016%3A202%3ATOC",
                "label": "《生态系统和生物多样性战略》"
              },
              {
                "value": "https://unfccc.int/resource/docs/convkp/conveng.pdf",
                "label": "《气候变化框架公约》"
              },
              {
                "value": "https://unfccc.int/resource/docs/convkp/kpeng.pdf",
                "label": "《京都议定书》"
              }
            ]
          },
          {
            "value": "法律法规",
            "label": "法律法规",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32000L0060",
                "label": "水框架指令2000/60/EC"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32010L0075",
                "label": "工业排放指令2010/75/EU"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A31994L0062",
                "label": "包装和包装废物指令1994/62/EC"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32008L0098",
                "label": "废物框架指令2008/98/EC"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A31999L0013",
                "label": "溶剂排放指令1999/13/EC"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A31992L0043",
                "label": "生物多样性和自然栖息地保护指令92/43/EEC"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32009L0128",
                "label": "植物保护产品指令2009/128/EC"
              },
              {
                "value": "",
                "label": ""
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32004L1935",
                "label": "食品接触材料指令2004/1935/EC"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32014R0517",
                "label": "氟利昂气体指令517/2014"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32013L0034",
                "label": "企业责任法中《欧盟 2020战略：在经济、环境和社会三方面推动智能、可持续和包容性增长》《企业信息披露指令》"
              }
            ]
          },
          {
            "value": "条例",
            "label": "条例",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/ALL/?uri=CELEX%3A32008R1005",
                "label": "欧盟渔业和海洋污染条例（EU Regulation 1005/2008）"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32012L0027",
                "label": "欧洲气候和能源框架法（European Climate and Energy Framework Law）"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32014R0304",
                "label": "欧盟水产养殖条例（EU Aquaculture Regulation 2014/304）"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32006R1367",
                "label": "欧盟环境纪录公开条例（EU Regulation 1367/2006）"
              }
            ]
          },
          {
            "value": "判例",
            "label": "判例",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32092L0043",
                "label": "天然保护法"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?qid=1623101610474&uri=CELEX:32019L1020",
                "label": "产品法案"
              },
              {
                "value": "",
                "label": ""
              },
            ]
          },
          {
            "value": "指南",
            "label": "指南",
            "children": [
              {
                "value": "https://ec.europa.eu/energy/topics/oil-gas-and-coal/liquefied-natural-gas_en",
                "label": "1. 欧盟液化天然气基础设施和燃料统一标准的技术指南"
              },
              {
                "value": "https://environment.ec.europa.eu/topics/air_en",
                "label": "2. 欧盟对大气污染物排放的在线监测和报告的指南及数据交换标准"
              },
              {
                "value": "https://echa.europa.eu/guidance-documents/guidance-on-chemical-safety-assessment",
                "label": "3. 欧盟有害化学物质评估的技术指南"
              },
               {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32000L0059",
                "label": "7. 欧盟船舶废物处理技术与标准细则指南"
              },
              {
                "value": "：https://ec.europa.eu/environment/industry/pdf/about_ippc/guidance_ippc.pdf",
                "label": "8. 欧盟对工业排放指令以及新工业污染控制指令的实施指南"
              },
              {
                "value": "https://ec.europa.eu/environment/nature/ecosystems/ecological_infrastructure.htm",
                "label": "9. 欧盟环境关键基础设施的生态设计指导方针"
              }
            ]
          }
        ]
      },
      {
        "value": "土地",
        "label": "土地",
        "children": [
          {
            "value": "条约",
            "label": "条约",
            "children": [
              {
                "value": "https://ec.europa.eu/trade/policy/countries-and-regions/countries/china/",
                "label": "欧盟与中国之间的投资协定"
              }
            ]
          },
          {
            "value": "法律法规",
            "label": "法律法规",
            "children": [
              {
                "value": "",
                "label": ""
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32014L0055 ",
                "label": "欧洲土地资源保护指令"
              },
              {
                "value": "https://eur-lex.europa.eu/LexUriServ/LexUriServ.do?uri=CELEX:32006L0042:EN:HTML",
                "label": "欧盟土地征收指令"
              },
              {
                "value": "https://eur-lex.europa.eu/eli/dir/2014/89/oj",
                "label": "关于欧盟土地使用和开发指令"
              },
            ]
          },
          {
            "value": "条例",
            "label": "条例",
            "children": [
              {
                "value": "https://ec.europa.eu/environment/soil/index_en.htm",
                "label": "欧盟土地保护条例"
              },
            ]
          },
          {
            "value": "判例法",
            "label": "判例法",
            "children": [
              {
                "value": "https://curia.europa.eu/jcms/jcms/j_6/",
                "label": "欧盟环境评估法（EIA）的判例法，案例包括：T-177/12、C-420/87和C-127/02"
              }
            ]
          },
            ]
          }
        ]
      },
      {
        "value": "投资",
        "label": "投资",
        "children": [
          {
            "value": "条约",
            "label": "条约",
            "children": [
              {
                "value": "https://rcepsec.org/",
                "label": "1《区域全面经济伙伴关系协定》（RCEP）第十二章：投资，包括投资政策、投资自由化和便利化等方面的规定。"
              },
              {
                "value": "https://www.efta.int/",
                "label": "2《欧洲自由贸易联盟》：投资与贸易领域的协调（第十三章 资本自由流动），投资保护（第十四章 知识产权保护和关于国民待遇、最惠国待遇的投资条款），讨论投资领域合作的机会（附录十三-E 欧洲自由贸易联盟国家和南美南方共同市场关于贸易、投资和创新合作的讨论）"
              }
            ]
          },
          {
            "value": "法律法规",
            "label": "法律法规",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32019R0459",
                "label": "1《欧盟外商直接投资审查条例》"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:32019L1023",
                "label": "3《简化债务重组和破产规则法规》"
              }
            ]
          },
          {
            "value": "条例",
            "label": "条例",
            "children": [
              {
                "value": "https://ec.europa.eu/docsroom/documents/41401",
                "label": "1《欧盟成员国关于外商直接投资审查的指引》"
              },
            ]
          },
          {
            "value": "判例",
            "label": "判例",
            "children": [
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?isOldUri=true&uri=CELEX:62011CJ0098",
                "label": "1，第C-98/11 P号案件 - 液晶面板制造商的价格操纵违反投资自由和贸易自由原则"
              },
              {
                "value": "https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?isOldUri=true&uri=CELEX:62016CJ0529",
                "label": "2，C-529/16 E和其他人诉欧洲委员会案，此案涉及到财政资助和国有企业剥离问题。"
              }
            ]
          },
          {
            "value": "指南",
            "label": "指南",
            "children": [
              {
                "value": "https://ec.europa.eu/commission/presscorner/detail/en/ip_19_719",
                "label": "1《投资保护指南》"
              },
              {
                "value": "https://ec.europa.eu/trade/policy/in-focus/eu-approach-investment-protection_en",
                "label": "3《 投资协定进程指南》"
              }
            ]
          }
        ]
      }
    ]
  },
 {
    "value": "美国（以联邦法律为主）",
    "label": "美国（以联邦法律为主）",
    "children": [
      {
        "value": "投资法律制度及其政策",
        "label": "投资法律制度及其政策",
        "children": [
          {
            "value": "机构：国防生产法产生 cfius",
            "label": "机构：国防生产法产生 CFIUS"
          },
          {
            "value": "投资方式",
            "label": "投资方式",
            "children": [
              {
                "value": "地方政府主管部门对接 cfius监管",
                "label": "地方政府主管部门对接 CFIUS监管"
              }
            ]
          },
          {
            "value": "投资法规",
            "label": "投资法规",
            "children": [
              {
                "value": "联邦",
                "label": "联邦",
                "children": [
                  {
                    "value": "https://wenku.so.com/d/085d85e1869e944ee430e27c268e0fd9",
                    "label": "1935年《社会保障法》及修正案"
                  }
                ]
              }
            ]
          },
          {
            "value": "敏感行业投资限制",
            "label": "敏感行业投资限制",
            "children": [
              {
                "value": "航空运输投票权百分之25 董事会三分之一",
                "label": "航空运输投票权百分之25 董事会三分之一"
              },
              {
                "value": "通信 禁止获得经营许可 严格限制投资",
                "label": "通信 禁止获得经营许可 严格限制投资"
              },
              {
                "value": "核电 仅限本国",
                "label": "核电 仅限本国"
              },
              {
                "value": "水电 允许外国控制的美国公司从事通航河流水电开发",
                "label": "水电 允许外国控制的美国公司从事通航河流水电开发"
              },
              {
                "value": "基础设施 对等原则",
                "label": "基础设施 对等原则"
              }
            ]
          },
          {
            "value": "对外优惠政策（各州具体决定）",
            "label": "对外优惠政策（各州具体决定）"
          },
          {
            "value": "特别经济区规定",
            "label": "特别经济区规定"
          }
        ]
      },
      {
        "value": "贸易法律制度",
        "label": "贸易法律制度",
        "children": [
          {
            "value": "贸易法规",
            "label": "贸易法规",
            "children": [
              {
                "value": "https://www.zsbeike.com/wap/jilu/10011450.html",
                "label": "1988年综合竞争贸易法"
              },
              {
                "value": "《h.r.875-2016年跨境贸易促进法》（h.r.875 - cross-border trade enhancement act of 2016）",
                "label": "《H.R.875-2016年跨境贸易促进法》（H.R.875 - Cross-Border Trade Enhancement Act of 2016）"
              },
              {
                "value": "《h.r.644-2015年贸易便利化和贸易执行法》（h.r.644 - trade facilitation and trade enforcement act of 2015）",
                "label": "《H.R.644-2015年贸易便利化和贸易执行法》（H.R.644 - Trade Facilitation and Trade Enforcement Act of 2015）"
              }
            ]
          },
          {
            "value": "进口管理制度",
            "label": "进口管理制度",
            "children": [
              {
                "value": "关税调节",
                "label": "关税调节"
              },
              {
                "value": "1972年海洋哺乳动物保护法",
                "label": "1972年海洋哺乳动物保护法"
              },
              {
                "value": "https://www.doc88.com/p-1184842883697.html",
                "label": "1962贸易拓展法"
              },
              {
                "value": "https://money.163.com/keywords/0/3/00310039003700345e748d3866136cd5/1.html",
                "label": "1974年贸易法122条款"
              }
            ]
          },
          {
            "value": "出口管理制度",
            "label": "出口管理制度",
            "children": [
              {
                "value": "https://www.sohu.com/a/277103236_100269542",
                "label": "1979年出口管理法"
              },
              {
                "value": "https://www.sohu.com/a/277103236_100269542",
                "label": "武器出口管制法案"
              },
              {
                "value": "联邦",
                "label": "联邦",
                "children": [
                  {
                    "value": "https://wenku.so.com/d/558747dfb5acffb1bb5a7dccfe053972",
                    "label": "《出口管制改革法案》"
                  },
                  {
                    "value": "https://zhuanlan.zhihu.com/p/426403382",
                    "label": "《出口管制条例》"
                  },
                  {
                    "value": "https://www.docin.com/p-877869049.html 
https://nlibvpn.bit.edu.cn/https/77726476706e69737468656265737421a1b94f993f2426477b1b9da099426d3695fe/Search/Results.html?query=List%20of%20Business%20Countries&isPremiumAdvanceSearch=False&jurisdiction=ALLFEDS&saveJuris=False&contentType=ALL&querySubmissionGuid=i0ad604ac0000018defcf8d67a0e0d6b4&startIndex=1&searchId=i0ad604ac0000018defcf8d67a0e0d6b4&kmSearchIdRequested=False&simpleSearch=False&isAdvancedSearchTemplatePage=False&skipSpellCheck=False&isTrDiscoverSearch=False&thesaurusSearch=False&thesaurusTermsApplied=False&ancillaryChargesAccepted=False&proviewEligible=False&eventingTypeOfSearch=FRM&trailingSpace=False&citationSortable=False&useNonBillableZoneClientId=False&transitionType=Search&contextData=%28sc.Default%29",
                    "label": "《商业管制清单》和《商业国家列表》"
                  }
                ]
              }
            ]
          },
          {
            "value": "https://qiaoyi.org/usashangyehuolu.html",
            "label": "反商业贿赂法规",
            "children": [
              {
                "value": "各州单独立法",
                "label": "各州单独立法"
              },
              {
                "value": "联邦",
                "label": "联邦",
                "children": [
                  {
                    "value": "https://baike.so.com/doc/6497384-6711099.html",
                    "label": "美国反海外腐败法案"
                  }
                ]
              }
            ]
          },
          {
            "value": "美国参加缔结的国际贸易条约、协定",
            "label": "美国参加缔结的国际贸易条约、协定",
            "children": [
              {
                "value": "多边条约（美国缔结时间顺序排列）",
                "label": "多边条约（美国缔结时间顺序排列）",
                "children": [
                  {
                    "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=XXII-1&chapter=22&clang=_en",
                    "label": "承认及执行外国仲裁裁决公约（UN）"
                  },
                  {
                    "value": "http://www.wcoomd.org/-/media/wco/public/global/pdf/about-us/legal-instruments/conventions-and-agreements/ata/pf_ata_conv_text.pdf?la=en",
                    "label": "货物凭A.T.A.报关单证册暂时进口的海关公约（WCO）"
                  },
                  {
                    "value": "http://tfs.mofcom.gov.cn/article/date/j/al/200212/20021200058437.shtml",
                    "label": "关于解决国家和他国国民之间投资争端公约（WBG）"
                  },
                  {
                    "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=X-3&chapter=10&clang=_en",
                    "label": "内陆国家过境贸易公约（UN）"
                  },
                  {
                    "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=XI-B-22&chapter=11&clang=_en",
                    "label": "国际易腐食品运输及其所用特别设备协定（易腐食品运输协定）（UN）"
                  },
                  {
                    "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=XI-A-9&chapter=11&clang=_en，http://www.wcoomd.org/en/topics/facilitation/instrument-and-tools/conventions/pf_revised_kyoto_conv.aspx",
                    "label": "集装箱关务公约（UN）    关于简化和协调海关业务制度的国际公约（京都公约）（WCO）"
                  },
                  {
                    "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=X-7&chapter=10&clang=_en",
                    "label": "联合国国际货物销售时效公约（UN）"
                  },
                  {
                    "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=XI-A-16&chapter=11&clang=_en",
                    "label": "＞关于国际公路货运通行证制度下国际货运海关公约（国际公路货运公约）（UN）"
                  },
                  {
                    "value": "https://www.wto.org/english/docs_e/legal_e/air-79_e.htm",
                    "label": "民用航空器贸易协议（WTO）"
                  },
                  {
                    "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=X-10&chapter=10&clang=_en",
                    "label": "联合国国际货物销售合同公约（UN）"
                  },
                  {
                    "value": "http://www.wcoomd.org/en/topics/nomenclature/instrument-and-tools/hs_convention.aspx",
                    "label": "商品名称及编码协调制度的国际公约（WCO）"
                  },
                  {
                    "value": "https://www.wto.org/english/docs_e/legal_e/06-gatt_e.htm／世贸组织乌拉圭回合谈判相关协定（wto）        https://www.wto.org/english/docs_e/legal_e/04-wto_e.htm",
                    "label": "1986年－1994年关贸总协定／世贸组织乌拉圭回合谈判相关协定（WTO）        建立世界贸易组织的马拉喀什协议» 1994年关税与贸易总协定（GATT）",
                    "children": [
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/14-ag_01_e.htm",
                        "label": "农业协议"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/15sps_01_e.htm",
                        "label": "实施卫生与植物卫生措施协议"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/16-tex_e.htm",
                        "label": "纺织品与服装协定» 技术性贸易壁垒协议"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/18-trims_e.htm https://www.wto.org/english/docs_e/legal_e/19-adp_01_e.htm",
                        "label": "与贸易有关的投资措施协议» 关于执行1994年关贸总协定第六条的协议（反倾销协议）"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/20-val_01_e.htm",
                        "label": "关于实施1994年关税与贸易总协定第七条的协定（海关估价协定）"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/21-psi_e.htm https://www.wto.org/english/docs_e/legal_e/rev-gpr-94_01_e.htm https://www.wto.org/english/docs_e/legal_e/22-roo_e.htm https://www.wto.org/english/docs_e/legal_e/23-lic_e.htm https://www.wto.org/english/docs_e/legal_e/24-scm_01_e.htm",
                        "label": "装运前检验协议» 政府采购协定» 原产地规则协议» 进口许可程序协议» 补贴与反补贴措施协议"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/25-safeg_e.htm，https://www.wto.org/english/tratop_e/serv_e/gatsintr_e.htm",
                        "label": "保障措施协议» 服务贸易总协定（GATS）"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/31bis_trips_01_e.htm",
                        "label": "与贸易有关的知识产权协定"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/28-dsu_e.htm",
                        "label": "关于争端解决规则与程序的谅解"
                      },
                      {
                        "value": "https://www.wto.org/english/docs_e/legal_e/29-tprm_e.htm https://www.wto.org/english/docs_e/legal_e/ibma-94_e.htm",
                        "label": "贸易政策审议机制» 国际牛肉协议"
                      },
                      {
                        "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=XIX-41-a&chapter=19&clang=_en",
                        "label": "1995年谷物贸易公约（UN）"
                      },
                      {
                        "value": "https://www.wto.org/english/tratop_e/serv_e/4prote_e.htm",
                        "label": "服务贸易总协定第四议定书（WTO）"
                      },
                      {
                        "value": "https://www.wto.org/english/tratop_e/serv_e/5prote_e.htm",
                        "label": "服务贸易总协定第五议定书（WTO）"
                      },
                      {
                        "value": "https://treaties.un.org/Pages/ViewDetails.aspx?src=TREATY&mtdsg_no=XIX-48&chapter=19&clang=_en",
                        "label": "粮食援助公约（2012年4月25日，伦敦） （UN）"
                      }
                    ]
                  }
                ]
              },
              {
                "value": "区域经济一体化条约",
                "label": "区域经济一体化条约",
                "children": [
                  {
                    "value": "https://ustr.gov/trade-agreements/free-trade-agreements/north-american-free-trade-agreement-nafta",
                    "label": "加拿大政府，墨西哥合众国政府和美利坚合众国政府间北美自由贸易协定（修订文本仍在谈判中）"
                  },
                  {
                    "value": "https://ustr.gov/trade-agreements/free-trade-agreements/cafta-dr-dominican-republic-central-america-fta/final-text",
                    "label": "中美洲自由贸易协定，签约其他国家包括哥斯达黎加、多米尼加共和国、萨尔瓦多、危地马拉、洪都拉斯、尼加拉瓜。"
                  },
                  {
                    "value": "https://ustr.gov/ttip",
                    "label": "跨大西洋贸易与投资伙伴关系协定（TTIP）（谈判中）"
                  }
                ]
              },
              {
                "value": "双边条约",
                "label": "双边条约",
                "children": [
                  {
                    "value": "双边投资协定",
                    "label": "双边投资协定",
                    "children": [
                      {
                        "value": "www.state.gov",
                        "label": "www.state.gov"
                      }
                    ]
                  },
                  {
                    "value": "自由贸易协定（12个签署国）",
                    "label": "自由贸易协定（12个签署国）",
                    "children": [
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/australian-fta/final-text",
                        "label": "澳大利亚(Australian FTA)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/bahrain-fta/final-text",
                        "label": "巴林(Bahrain F TA)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/chile-fta/final-text",
                        "label": "智利 (Chile FT A)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/colombia-fta/final-text",
                        "label": "哥伦比亚(Colombia TPA)"
                      },
                      {
                        "value": "https://ustr.gov/sites/default/files/files/agreements/FTA/israel/Israel%20FTA.pdf",
                        "label": "以色列(Israel F TA)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/jordan-fta/final-text",
                        "label": "约旦(Jordan F TA)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/korus-fta/final-text",
                        "label": "韩国(KORUS F TA)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/morocco-fta/final-text",
                        "label": "摩洛哥(Morocco FTA)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/oman-fta/final-text",
                        "label": "阿曼(Oman FT A)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/panama-tpa/final-text",
                        "label": "巴拿马(PanamaTPA)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/peru-tpa/final-text",
                        "label": "秘鲁(Peru TP A)"
                      },
                      {
                        "value": "https://ustr.gov/trade-agreements/free-trade-agreements/singapore-fta/final-text",
                        "label": "新加坡(Singapore FTA)"
                      }
                    ]
                  }
                ]
              }
            ]
          }
        ]
      },
      {
        "value": "证券交易",
        "label": "证券交易",
        "children": [
          {
            "value": "https://wenku.so.com/d/0b7d3e089577ec5b495162a7f1fc158f",
            "label": "1933证券法"
          },
          {
            "value": "https://wenku.so.com/d/6a9142c3e1d2a07caf191087d23f6eb4",
            "label": "1934证券交易法"
          },
          {
            "value": "https://www.doc88.com/p-9833374666069.html",
            "label": "1940投资公司法"
          },
          {
            "value": "https://wenku.so.com/d/fcad5cf0a0f3969ca712a4ef309c5153?src=ob_zz_juhe360wenku",
            "label": "1950年《标准公司法》11-13章中关于收购上市公司的规定"
          }
        ]
      },
      {
        "value": "劳动",
        "label": "劳动",
        "children": [
          {
            "value": "联邦",
            "label": "联邦",
            "children": [
              {
                "value": "https://www.110.com/fagui/law_14212.html",
                "label": "《国家劳资关系法案》（1935年）"
              },
              {
                "value": "https://wenku.so.com/d/6cb551321911e321fbeb25f605f6a121?src=ob_zz_juhe360wenku",
                "label": "《1964年民权法案第七章》（1964）"
              },
              {
                "value": "https://wenku.so.com/d/6ef7bd06a8fa23158eb7a88f6c592714",
                "label": "《1967年反劳动者年龄歧视法》（ 1967）"
              },
              {
                "value": "https://www.docin.com/p-2003113555.html",
                "label": "《美国残疾人法案》（ 1990）"
              },
              {
                "value": "https://www.docin.com/p-1006844006.html",
                "label": "《家庭与医疗休假法》"
              },
              {
                "value": "https://wenku.so.com/d/50f927015bf8819f40596b0de1f83261",
                "label": "《公平劳动标准法》"
              },
              {
                "value": "https://www.docin.com/p-2333017216.html",
                "label": "《军人就业及再就业权利法》"
              },
              {
                "value": "https://www.zsbeike.com/bk/699945.html",
                "label": "《同酬法案》"
              },
              {
                "value": "https://www.docin.com/p-2442059349.html",
                "label": "《雇员退休收入保障法》"
              },
              {
                "value": "https://www.docin.com/p-699885910.html",
                "label": "《综合预算协调法》"
              },
              {
                "value": "https://max.book118.com/html/2016/0315/37707231.shtm",
                "label": "《1970年职业安全和健康法》"
              },
              {
                "value": "https://cdmd.cnki.com.cn/Article/CDMD-10040-1011170847.htm",
                "label": "《移民改革及控制法案》"
              },
              {
                "value": "https://wenku.so.com/d/4f7511911a9809d32224de44caa91414",
                "label": "《劳资报告与公告法》"
              }
            ]
          },
          {
            "value": "纽约州",
            "label": "纽约州",
            "children": [
              {
                "value": "https://zh.dol.ny.gov/labor-standards-0",
                "label": "《纽约州劳动法》"
              },
              {
                "value": "https://www.nyc.gov/assets/dca/downloads/pdf/about/PaidSickLeave-EmployerOnePager-SimplifiedChinese.pdf",
                "label": "《带薪安全和病假法案》"
              },
              {
                "value": "https://wenku.so.com/d/8cc8c0e98ba3999ed783c91f6c484b7e",
                "label": "1935年《社会保障法》及修正案"
              }
            ]
          }
        ]
      },
      {
        "value": "环境保护",
        "label": "环境保护",
        "children": [
          {
            "value": "联邦",
            "label": "联邦",
            "children": [
              {
                "value": "https://www.doc88.com/p-3037600672098.html",
                "label": "《联邦水污染控制法》（1948年）"
              },
              {
                "value": "https://www.docin.com/p-532834244.html",
                "label": "《联邦杀虫剂、灭菌剂及灭鼠剂法》（1947年）"
              },
              {
                "value": "https://max.book118.com/html/2022/0905/6202044043004233.shtm",
                "label": "《原子能法》（1954年）"
              },
              {
                "value": "https://xueshu.baidu.com/usercenter/paper/show?paperid=5b6fa1d79616bf2b44888f3a1c63a485&site=xueshu_se",
                "label": "《联邦大气污染控制法》（1955年）"
              },
              {
                "value": "https://www.docin.com/p-97146516.html",
                "label": "《联邦有害物质法》（1960年）"
              },
              {
                "value": "https://wikipredia.net/zh/Fish_and_Wildlife_Coordination_Act",
                "label": "《鱼类和野生生物协调法》（1965年）"
              },
              {
                "value": "https://wikipredia.net/zh/Clean_Air_Act_(United_States)",
                "label": "《空气质量法》（1967年）"
              },
              {
                "value": "https://www.rivers.gov/documents/act/complete-act.pdf",
                "label": "《自然和风景河流法》（1968年）"
              },
              {
                "value": "https://wikipredia.net/zh/National_Environmental_Education_Act",
                "label": "《美国环境教育法》（1970年）"
              },
              {
                "value": "https://www.pkulaw.cn/fulltext_form.aspx?Gid=1ce0af4b6304721be88d0e556ef6911abdfb",
                "label": "《海岸带管理法》（1972年）"
              },
              {
                "value": "https://wikipredia.net/zh/Marine_Mammal_Protection_Act",
                "label": "《海洋哺乳动物保护法》（1972年）"
              },
              {
                "value": "https://www.sgpjbg.com/baogao/40702.html",
                "label": "《海洋保护研究及禁渔区法》（1972年）"
              },
              {
                "value": "https://wikipredia.net/zh/Federal_Insecticide,_Fungicide,_and_Rodenticide_Act",
                "label": "《联邦环境杀虫剂控制法》（1972年）"
              },
              {
                "value": "https://www.docin.com/p-532834927.html",
                "label": "《噪声控制法》（1972年）"
              },
              {
                "value": "https://www.doc88.com/p-0827889648310.html",
                "label": "《安全饮用水法》（1974年）"
              },
              {
                "value": "https://wikipredia.net/zh/Endangered_Species_Act_of_1973",
                "label": "《濒危物种法》（1973年）"
              },
              {
                "value": "https://www.doc88.com/p-378887687818.html",
                "label": "《联邦土地政策及管理法》（1976年）"
              },
              {
                "value": "https://www.epa.gov/laws-regulations/summary-toxic-substances-control-act",
                "label": "《有毒物质运输法》（1975年）"
              },
              {
                "value": "https://www.epa.gov/rcra",
                "label": "《资源保护与回收法》（1976年）"
              },
              {
                "value": "https://www.epa.gov/laws-regulations/summary-toxic-substances-control-act",
                "label": "《有毒物质控制法》（1976年）"
              },
              {
                "value": "https://www.epa.gov/sites/default/files/2015-06/documents/title_iv_-acid_deposition_control.pdf",
                "label": "《酸雨法》（1980年）"
              },
              {
                "value": "https://nepis.epa.gov/Exe/ZyNET.exe/P100SUB1.TXT?ZyActionD=ZyDocument&Client=EPA&Index=1991+Thru+1994&Docs=&Query=&Time=&EndTime=&SearchMethod=1&TocRestrict=n&Toc=&TocEntry=&QField=&QFieldYear=&QFieldMonth=&QFieldDay=&IntQFieldOp=0&ExtQFieldOp=0&XmlQuery=&File=D%3A%5Czyfiles%5CIndex%20Data%5C91thru94%5CTxt%5C00000034%5CP100SUB1.txt&User=ANONYMOUS&Password=anonymous&SortMethod=h%7C-&MaximumDocuments=1&FuzzyDegree=0&ImageQuality=r75g8/r75g8/x150y150g16/i425&Display=hpfr&DefSeekPage=x&SearchBack=ZyActionL&Back=ZyActionS&BackDesc=Results%20page&MaximumPages=1&ZyEntry=1&SeekPage=x&ZyPURL",
                "label": "《生物量及酒精燃料法》（1980年）"
              },
              {
                "value": "https://bjgy.bjcourt.gov.cn/article/detail/2009/06/id/869777.shtml",
                "label": "《固体废物处置法》（1980年）"
              },
              {
                "value": "https://www.neilandrew.com/what-is-the-nuclear-waste-policy-act-5112440#",
                "label": "《核废弃物政策法》（1982年）"
              }
            ]
          }
        ]
      },
      {
        "value": "(外企)工程承包规定",
        "label": "(外企)工程承包规定",
        "children": [
          {
            "value": "https://www.govinfo.gov/content/pkg/COMPS-10384/pdf/COMPS-10384.pdf",
            "label": "一般商法"
          },
          {
            "value": "https://www.whitehouse.gov/wp-content/uploads/2022/05/BUILDING-A-BETTER-AMERICA-V2.pdf",
            "label": "外企获得土地规定",
            "children": [
              {
                "value": "https://www.docin.com/p-2421133374.html",
                "label": "土地法"
              },
              {
                "value": "土地买卖各州制定",
                "label": "土地买卖各州制定"
              }
            ]
          }
        ]
      },
      {
        "value": "知识产权保护",
        "label": "知识产权保护",
        "children": [
          {
            "value": "https://wenku.so.com/d/8646a42a38b8aa443d11e14812315769?src=ob_zz_juhe360wenku",
            "label": "专利法"
          },
          {
            "value": "https://wenku.so.com/d/4347a11776e3c74ff40c4c91239c0227?src=ob_zz_juhe360wenku",
            "label": "商标法"
          },
          {
            "value": "https://wenku.so.com/d/29694c78843b380a73a1b3d7e33d0c97?src=ob_zz_juhe360wenku",
            "label": "版权法"
          },
          {
            "value": "https://wenku.so.com/d/795ad1815e65caadc4581093c33499c9",
            "label": "反不正当竞争法"
          },
          {
            "value": "https://www.wipo.int/wipolex/zh/legislation/details/14313",
            "label": "乌拉圭回合协议法"
          },
          {
            "value": "https://www.wipo.int/wipolex/zh/legislation/details/12912",
            "label": "莱希-史密斯美国发明创造法"
          }
        ]
      },
      {
        "value": "反垄断",
        "label": "反垄断",
        "children": [
          {
            "value": "联邦",
            "label": "联邦",
            "children": [
              {
                "value": "https://www.doc88.com/p-7018944388412.html",
                "label": "《综合贸易与竞争法》（1988）"
              },
              {
                "value": "https://wiki.mbalib.com/wiki/Sherman_Antitrust_Act",
                "label": "《谢尔曼法》（1890）"
              },
              {
                "value": "https://baike.so.com/doc/9758500-10105100.html",
                "label": "《克莱顿法》（1914）"
              },
              {
                "value": "https://investors.wiki/zh/celler-kefauver-act",
                "label": "《塞勒——凯弗维尔反兼并法》（1950）"
              },
              {
                "value": "https://max.book118.com/html/2017/0504/104207487.shtm",
                "label": "《哈特—斯科特—罗迪诺反托拉斯改进法》（1976）"
              },
              {
                "value": "https://lawecommons.luc.edu/cgi/viewcontent.cgi?article=2066&context=luclj",
                "label": "《反托拉斯程序修订法》（1980）"
              }
            ]
          },
          {
            "value": "州",
            "label": "州",
            "children": [
              {
                "value": "反垄断",
                "label": "反垄断",
                "children": [
                  {
                    "value": "https://law.justia.com/codes/new-york/2006/general-business/idx_gbs0a33.html",
                    "label": "《纽约州特许经营法》"
                  },
                  {
                    "value": "https://law.justia.com/codes/new-york/2006/general-business/idx_gbs0a33.html",
                    "label": "《纽约特许经营条例》"
                  }
                ]
              }
            ]
          }
        ]
      },
      {
        "value": "争议解决",
        "label": "争议解决",
        "children": [
          {
            "value": "商务纠纷救济路径",
            "label": "商务纠纷救济路径",
            "children": [
              {
                "value": "适用法律的确定：合同规定",
                "label": "适用法律的确定：合同规定",
                "children": [
                  {
                    "value": "国际仲裁",
                    "label": "国际仲裁"
                  },
                  {
                    "value": "当地法院",
                    "label": "当地法院"
                  }
                ]
              }
            ]
          }
        ]
      },
      {
        "value": "安全",
        "label": "安全",
        "children": [
          {
            "value": "投资安全审查：",
            "label": "投资安全审查："
          },
          {
            "value": "联邦",
            "label": "联邦"
          },
          {
            "value": "州（纽约州为例）",
            "label": "州（纽约州为例）",
            "children": [
              {
                "value": "https://zh.ag.ny.gov/resources/organizations/data-breach-reporting/shield-act",
                "label": "2005《信息安全漏洞和通知法》"
              },
              {
                "value": "https://zh.ag.ny.gov/resources/organizations/data-breach-reporting/shield-act",
                "label": "2019《制止黑客攻击和改善电子数据法》"
              }
            ]
          }
        ]
      },
      {
        "value": "（基与美国特殊性）补充：国际组织",
        "label": "（基与美国特殊性）补充：国际组织",
        "children": [
          {
            "value": "联合国",
            "label": "联合国",
            "children": [
              {
                "value": "https://www.icao.int/about-icao/Pages/default.aspx",
                "label": "1. 国际民用航空组织（ICAO)"
              },
              {
                "value": "https://www.ifad.org/en",
                "label": "2. 国际农业发展基金（IFAD)"
              },
              {
                "value": "https://www.ilo.org/global/lang--en/index.htm",
                "label": "3. 国际劳工组织（ILO)"
              },
              {
                "value": "https://www.imf.org/en/home",
                "label": "4. 国际货币基金组织（IMF)"
              },
              {
                "value": "https://www.imo.org/en/",
                "label": "5. 国际海事组织（IMO）"
              },
              {
                "value": "https://www.itu.int/zh/Pages/default.aspx",
                "label": "6. 国际电信联盟（ITU）"
              },
              {
                "value": "https://www.unesco.org/zh/brief",
                "label": "7. 联合国教科文组织"
              },
              {
                "value": "https://www.fao.org/home/zh",
                "label": "8.联合国粮食及农业组织UNFAO"
              },
              {
                "value": "https://www.unido.org",
                "label": "9. 联合国工业发展组织(UNIDO)"
              },
              {
                "value": "https://www.unwto.org/",
                "label": "1 0世界旅游组织（UNWTO)"
              },
              {
                "value": "https://www.upu.int/en/Universal-Postal-Union",
                "label": "11万国邮政联盟(UPU)"
              },
              {
                "value": "https://www.worldbank.org/en/home",
                "label": "12世界银行2(WBG)"
              },
              {
                "value": "https://www.who.int/zh",
                "label": "13世界卫生组织（WHO)"
              },
              {
                "value": "https://www.wipo.int/portal/zh/",
                "label": "14世界知识产权组织（WIPO)"
              },
              {
                "value": "https://wmo.int/",
                "label": "15世界气象组织（WMO)"
              }
            ]
          },
          {
            "value": "https://www.wto.org/",
            "label": "世界贸易组织"
          },
          {
            "value": "https://www.wcoomd.org/",
            "label": "世界海关组织",
            "children": [
              {
                "value": "http://xian.customs.gov.cn/customs/ztzl86/302310/5366122/gjmylyflgf/gjmyzbpgsjdgjtxxdx/5382624/index.html",
                "label": "海关国际条约"
              },
              {
                "value": "协调制度公约",
                "label": "协调制度公约"
              }
            ]
          }
        ]
      }
    ]
  }
]
      
</script>