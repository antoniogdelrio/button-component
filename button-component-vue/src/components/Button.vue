<template>
  <button 
    class="btn"
    v-bind:class="[
      btnColor,
      btnSize,
      btnShadow,
      btnVariant,
      btnDisabled
    ]"
  >
    <i v-if="startIcon" v-bind:class="startIcon"></i>
    {{innerText}}
    <i v-if="endIcon" v-bind:class="endIcon"></i>
  </button>
</template>

<script>

export default {
  name: 'Button',
  data: function(){
    return{
      btnColor: `btn-${this.color}`,
      btnSize: `btn-${this.size}`,
      btnShadow: this.disableShadow ? 'btn-no-shadow' : null,
      btnVariant: `btn-${this.variant}`,
      btnDisabled: this.disabled ? 'btn-disabled' : null,
    }
  },
  props: {
    variant: {
      type: String,
      default: "text"
    },
    disableShadow: {
      type: Boolean,
      default: false
    },
    disabled: {
      type: Boolean,
      default: false
    },
    startIcon: String,
    endIcon: String,
    size: {
      type: String,
      default: "md"
    },
    color: {
      type: String,
      default: "default"
    },
    innerText: {
      type: String,
      default: "Default"
    }
  }
}
</script>

<style scoped>
button{
  border: none;
  margin: 0;
  padding: 0;
  width: auto;
  overflow: visible;

  background: transparent;

  color: inherit;
  font: inherit;

  line-height: normal;

  -webkit-font-smoothing: inherit;
  -moz-osx-font-smoothing: inherit;

  -webkit-appearance: none;
}

.btn {
  border-radius: 6px;
  box-shadow: 0px 2px 3px rgba(51, 51, 51, 0.2);
}
.btn:hover{
  cursor: pointer;
}

.btn.btn-no-shadow {
  box-shadow: none;
}

.btn.btn-disabled{
  opacity: 0.5;
}

.btn.btn-sm {
  padding: 6px 12px;
}
.btn.btn-md {
  padding: 8px 16px;
}
.btn.btn-lg {
  padding: 11px 22px;
}

.btn.btn-default {
  --btnColor: #E0E0E0;
  --btnHoverColorText: #AEAEAE;
  --btnHoverColorOutline: #AEAEAE;
  color: #3F3F3F;
}
.btn.btn-primary {
  --btnColor: #2962FF;
  --btnHoverColorText: #0039CB;
  --btnHoverColorOutline: #d2deff;
  color: #fff;
}
.btn.btn-secondary {
  --btnColor: #455A64;
  --btnHoverColorText: #1C313A;
  --btnHoverColorOutline: #cecece;
  color: #fff;
}
.btn.btn-danger {
  --btnColor: #D32F2F;
  --btnHoverColorText: #9A0007;
  --btnHoverColorOutline: #ffd2d4;
  color: #fff;
}

.btn.btn-text{
  border: none;
  background-color: var(--btnColor);
}
.btn.btn-text:hover, .btn.btn-text:focus{
  background-color: var(--btnHoverColorText);
}
.btn.btn-outline{
  border: 1px solid var(--btnColor);
  color: var(--btnColor);
  background-color: #fff;
}
.btn.btn-outline:hover, .btn.btn-outline:focus{
  background-color: var(--btnHoverColorOutline);
}

</style>
