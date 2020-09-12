<template>
  <c-stack spacing="5" my="8" mx="auto" :max-w="['90vw', '90vw', '4xl']">
    <c-stack
      v-for="(job, i) in jobs"
      :key="i"
      px="6"
      py="4"
      shadow="sm"
      rounded="md"
      bg="white"
    >
      <c-flex :flex-dir="['column', 'colmun', 'row']" :align="['flex-start','flex-start', 'center']" justify="space-between">
        <c-heading as="h3">
          {{ job.title }}
        </c-heading>
        <c-flex>
          <c-text color="gray.600">
            {{ job.companyName }}
          </c-text>
          <c-divider orientation="vertical" />
          <p v-chakra color="purple.500" font-weight="bold">
            {{ job.companySize }}
          </p>
        </c-flex>
      </c-flex>
      <c-text color="gray.500">
        {{ job.description }}
      </c-text>
      <c-divider border-color="purple.200" />
      <c-stack align="center" is-inline>
        <c-text>
          $ {{ job.salary }}
        </c-text>
        <c-box bg="purple.300" w="1" h="1" rounded="full" />
        <c-text>
          {{ job.remote ? 'Remote' : 'On-site' }}
        </c-text>
        <c-box bg="purple.300" w="1" h="1" rounded="full" />
        <c-text>
          {{ job.location }}
        </c-text>
      </c-stack>
    </c-stack>
  </c-stack>
</template>

<script>
import jobs from '../jobs.json'

export default {
  computed: {
    jobs: () => jobs
  }
}
</script>
