<template>
  <div>
    <treeselect
      :multiple="true"
      :options="options"
      :value-consists-of="valueConsistsOf"
      :allow-single-child="true"
      v-model="value"
      />
    <treeselect-value :value="value" />
    <p><strong>Value consists of:</strong></p>
    <p class="options">
      <label><input type="radio" value="ALL" v-model="valueConsistsOf">All</label><br>
      <label><input type="radio" value="BRANCH_PRIORITY" v-model="valueConsistsOf">Branch priority</label><br>
      <label><input type="radio" value="LEAF_PRIORITY" v-model="valueConsistsOf">Leaf priority</label><br>
      <label><input type="radio" value="ALL_WITH_INDETERMINATE" v-model="valueConsistsOf">All with indeterminate</label>
    </p>
  </div>
</template>

<script>
  export default {
    data: () => ({
      value: [ 'team-i' ],
      valueConsistsOf: 'BRANCH_PRIORITY',
      options: [ {
        id: 'company',
        label: 'Company 🏢',
        children: [ {
          id: 'team-i',
          label: 'Team I 👥',
          children: [ {
            id: 'person-a',
            label: 'Person A 👱',
          }, {
            id: 'person-b',
            label: 'Person B 🧔',
          }, {
            id: 'person-c',
            label: 'Person C 👳',
          } ],
        }, {
          id: 'team-ii',
          label: 'Team II 👥',
          children: [ {
            id: 'person-d',
            label: 'Person D 👧',
          } ],
        }, {
          id: 'person-e',
          label: 'Person E 👩',
        } ],
      } ],
    }),
  }
</script>
