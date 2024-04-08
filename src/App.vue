<script setup>
import { ref } from "vue";
import TreeCollapse from "./components/TreeCollapse.vue";
import Table from "./components/Table.vue";

// Tree Collapse
let tree = ref({
  label: "MARKA",
  nodes: [
    {
      label: "Daewoo",
      nodes: [
        {
          label: "Nexia",
          nodes: [
            {
              label: "Zapchastlar",
              nodes: [
                {
                  label: "Tugadi",
                },
              ],
            },
          ],
        },
      ],
    },
    {
      label: "BMW",
      nodes: [
        {
          label: "Diskalar",
        },
      ],
    },
  ],
});

// Table
const tableColumns = ["Name", "Age", "Address", "Tags", "Action"];
const tableData = [
  {
    name: "John Doe",
    age: 32,
    address: "California",
    tags: ["nice", "developer"],
    action: ["invite", "delete", "more"],
  },
  {
    name: "Jane Doe",
    age: 19,
    address: "New York",
    tags: ["loser"],
    action: ["invite", "delete", "more"],
  },
  {
    name: "Nurjahon Dev",
    age: 26,
    address: "Tashkent",
    tags: ["noob", "developer"],
    action: ["invite", "delete", "more"],
  },
];
</script>

<template>
  <main class="container py-10 px-4">
    <div class="flex w-full justify-center">
      <Table :columns="tableColumns" :data="tableData" />
    </div>

    <br />
    <hr />
    <br />

    <div class="flex justify-center">
      <div class="">
        <TreeCollapse :label="tree.label" :nodes="tree.nodes" />
      </div>
    </div>
  </main>
</template>
