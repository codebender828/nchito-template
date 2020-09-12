<template>
  <c-box as="section">
    <c-stack
      as="header"
      color="white"
      justify="center"
      align="center"
      flex-dir="column"
      bg="green.500"
      :min-h="['60vh', '60vh', '60vh']"
      spacing="5"
    >
      <c-heading as="h1" font-size="4em">
        Find and post jobs!
      </c-heading>
      <c-text text-align="center" font-size="lg">
        Lorem ipsum dolor sit amet consectetur adipisicing elit.
      </c-text>
      <c-input-group>
        <c-input-left-element><c-icon name="search" color="gray.300" /></c-input-left-element>
        <c-input focus-border-color="purple.300" type="search" placeholder="Search job" />
      </c-input-group>
      <c-button size="lg" variant-color="purple" @click="isOpen = true">
        Create New Job
      </c-button>
    </c-stack>
    <c-drawer :is-open="isOpen" placement="right" :on-close="close" :initial-focus-ref="()=>$refs.inputInsideModal">
      <c-drawer-overlay />
      <c-drawer-content>
        <c-drawer-close-button />
        <c-drawer-header shadow="md" font-size="2xl">
          Post New Job
        </c-drawer-header>

        <c-drawer-body overflow-y="auto">
          <n-post-job-form />
        </c-drawer-body>

        <c-drawer-footer shadow="md">
          <c-button variant-color="purple" variant="outline" mr="3" @click="isOpen = false">
            Cancel
          </c-button>
          <c-button variant-color="purple" @click="handleSave">
            Save
          </c-button>
        </c-drawer-footer>
      </c-drawer-content>
    </c-drawer>
  </c-box>
</template>

<script>
export default {
  data () {
    return {
      isOpen: false
    }
  },
  methods: {
    close () {
      this.isOpen = false
    },
    handleSave () {
      this.close()
      this.$toast({
        title: 'Success',
        variant: 'subtle',
        description: 'New job post created!',
        status: 'success',
        duration: 10000
      })
    }
  }
}
</script>
