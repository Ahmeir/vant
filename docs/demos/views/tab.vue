<template>
  <demo-section>
    <demo-block :title="$t('basicUsage')">
      <van-tabs :active="active">
        <van-tab :title="$t('tab') + index" v-for="index in tabs" :key="index">
          {{ $t('content') }} {{ index }}
        </van-tab>
      </van-tabs>
    </demo-block>

    <demo-block :title="$t('title2')">
      <van-tabs>
        <van-tab v-for="index in 8" :title="$t('tab') + index" :key="index">
          {{ $t('content') }} {{ index }}
        </van-tab>
      </van-tabs>
    </demo-block>

    <demo-block :title="$t('title3')">
      <van-tabs @disabled="onClickDisabled">
        <van-tab v-for="index in 4" :title="$t('tab') + index" :disabled="index === 2" :key="index">
          {{ $t('content') }} {{ index }}
        </van-tab>
      </van-tabs>
    </demo-block>

    <demo-block :title="$t('title4')">
      <van-tabs type="card">
        <van-tab v-for="index in 4" :title="$t('tab') + index" :key="index">
          {{ $t('content') }} {{ index }}
        </van-tab>
      </van-tabs>
    </demo-block>

    <demo-block :title="$t('title5')">
      <van-tabs @click="handleTabClick">
        <van-tab v-for="index in 4" :title="$t('tab') + index" :key="index">
          {{ $t('content') }} {{ index }}
        </van-tab>
      </van-tabs>
    </demo-block>

    <demo-block :title="$t('title6')">
      <van-tabs :active="active" sticky>
        <van-tab :title="$t('tab') + index" v-for="index in tabs" :key="index">
          {{ $t('content') }} {{ index }}
        </van-tab>
      </van-tabs>
    </demo-block>

    <demo-block :title="$t('title7')">
      <van-tabs :active="active">
        <van-tab v-for="index in 2" :key="index">
          <div slot="title">
            <van-icon name="more-o" />{{ $t('tab') }}
          </div>
          {{ $t('content') }} {{ index }}
        </van-tab>
      </van-tabs>
    </demo-block>
  </demo-section>
</template>

<script>
export default {
  i18n: {
    'zh-CN': {
      tab: '选项 ',
      title2: '横向滚动',
      title3: '禁用标签',
      title4: '样式风格',
      title5: '点击事件',
      title6: '粘性布局',
      title7: '自定义标签'
    },
    'en-US': {
      tab: 'Tab ',
      content: 'content of tab',
      title2: 'Swipe Tabs',
      title3: 'Disabled Tab',
      title4: 'Card Style',
      title5: 'Click Event',
      title6: 'Sticky',
      title7: 'Custom Tab'
    }
  },

  data() {
    return {
      active: 2,
      tabs: [1, 2, 3, 4]
    };
  },

  methods: {
    onClickDisabled() {
      Toast('Disabled!');
    },

    handleTabClick(index) {
      Toast(index);
    }
  }
};
</script>

<style lang="postcss">
.demo-tab {
  margin-bottom: 700px;

  .van-tab .van-icon {
    margin-right: 5px;
    vertical-align: -2px;
  }

  .van-tab__pane {
    background-color: #fff;
    padding: 20px;
  }

  .van-tabs--card .van-tab__pane {
    background-color: transparent;
  }

  .custom-tabwrap .van-tab-active {
    color: #20a0ff;
  }
  .custom-tabwrap .van-tabs-nav-bar {
    background: #20a0ff;
  }
  .custom-pane {
    text-align: center;
    height: 50px;
    line-height: 50px;
  }

  .van-doc-demo-block:last-child {
    .van-tab__pane {
      padding: 50px 20px;
    }
  }
}
</style>
