<template>
  <div :class="`${prefixCls}-wrapper`">
    <div :class="prefixCls" :style="{ height: `${mergedStrokeWidth}px` }">
      <div
        v-for="(active, index) of stepList"
        :key="index"
        :class="[
          `${prefixCls}-item`,
          {
            [`${prefixCls}-item-active`]: active,
          },
        ]"
        :style="{
          backgroundColor: active ? color : trackColor,
        }"
      />
    </div>
    <div v-if="showText" :class="`${prefixCls}-text`">
      <slot name="text" :percent="percent">
        {{ `${percent * 100}%` }}
        <icon-exclamation-circle-fill v-if="status === 'danger'" />
      </slot>
    </div>
  </div>
</template>

<script lang="ts">
import { computed, defineComponent, PropType } from 'vue';
import { getPrefixCls } from '../_utils/global-config';
import IconExclamationCircleFill from '../icon/icon-exclamation-circle-fill';

export default defineComponent({
  name: 'ProgressSteps',
  components: {
    IconExclamationCircleFill,
  },
  props: {
    steps: {
      type: Number,
      default: 0,
    },
    percent: {
      type: Number,
      default: 0,
    },
    size: {
      type: String,
    },
    color: {
      type: [String, Object],
      default: undefined,
    },
    trackColor: String,
    strokeWidth: {
      type: Number,
    },
    status: {
      type: String,
      default: undefined,
    },
    showText: {
      type: Boolean,
      default: true,
    },
  },
  setup(props) {
    const prefixCls = getPrefixCls('progress-steps');

    const mergedStrokeWidth = computed(() =>
      props.strokeWidth ?? props.size === 'small' ? 8 : 4
    );

    const stepList = computed(() =>
      [...Array(props.steps)].map((_, index) => {
        return props.percent > 0 && props.percent >= (1 / props.steps) * index;
      })
    );

    return {
      prefixCls,
      stepList,
      mergedStrokeWidth,
    };
  },
});
</script>
