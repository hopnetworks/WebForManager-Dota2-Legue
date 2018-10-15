<template>
  <div className="analysis-page">
        <FixedTable />
      </div>
</template>

<script>
import FixedTable from './components/FixedTable';

export default {
  name: 'Analysis',
  components: {
    FixedTable,
  },
};
</script>
