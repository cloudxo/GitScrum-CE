<script>
import MasterHeader from '@layouts/partials/header'
import MasterHeaderMenuProject from '@layouts/partials/header-menu-project'

export default {
  components: {
    MasterHeader,
    MasterHeaderMenuProject,
  },
  data() {
    return {
      user: [],
      
    }
  },
  methods: {},
}
</script>

<template>
<div>
  <MasterHeader >
    <MasterHeaderMenuProject v-if="$route.params.projectSlug" slot="submenu" :background="true"></MasterHeaderMenuProject>
  </MasterHeader>

  <div id="page-padding-left">
    <div id="header-project-area" class="d-flex justify-content-between align-items-center tpl-main-project-area subheader">
      <div>
        <slot name="header-left"></slot>
      </div>
      <div>
        <slot name="header-right"></slot>
      </div>
    </div>
    <div id="page-content" class="container-fluid">
      <div style="max-width: 100%;overflow-x: auto;overflow-y: hidden;padding: 8px 15px 0 20px;min-height: calc(100vh - 0 );">
        <div class="row">
          <slot name="content"></slot>
        </div>
      </div>
    </div>
  </div>
</div>
</template>
