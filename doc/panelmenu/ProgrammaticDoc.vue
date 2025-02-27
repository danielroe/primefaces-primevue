<template>
    <DocSectionText v-bind="$attrs">
        <p>
            If the menuitem has a <i>key</i> defined, PanelMenu state can be controlled programmatically with the <i>expandedKeys</i> property that defines the keys that are expanded. This property is a Map instance whose key is the key of a node and
            value is a boolean. Note that <i>expandedKeys</i> also supports two-way binding with the v-model directive.
        </p>
    </DocSectionText>
    <div class="card flex flex-column align-items-center">
        <div class="mb-3">
            <Button type="button" icon="pi pi-plus" label="Expand All" @click="expandAll" class="mr-2" />
            <Button type="button" icon="pi pi-minus" label="Collapse All" @click="collapseAll" />
        </div>
        <PanelMenu v-model:expandedKeys="expandedKeys" :model="items" class="w-full md:w-25rem" />
    </div>
    <DocSectionCode :code="code" />
</template>

<script>
export default {
    data() {
        return {
            expandedKeys: {},
            items: [
                {
                    key: '0',
                    label: 'File',
                    icon: 'pi pi-fw pi-file',
                    items: [
                        {
                            key: '0_0',
                            label: 'New',
                            icon: 'pi pi-fw pi-plus',
                            items: [
                                {
                                    key: '0_0_0',
                                    label: 'Bookmark',
                                    icon: 'pi pi-fw pi-bookmark'
                                },
                                {
                                    key: '0_0_1',
                                    label: 'Video',
                                    icon: 'pi pi-fw pi-video'
                                }
                            ]
                        },
                        {
                            key: '0_1',
                            label: 'Delete',
                            icon: 'pi pi-fw pi-trash'
                        },
                        {
                            key: '0_2',
                            label: 'Export',
                            icon: 'pi pi-fw pi-external-link'
                        }
                    ]
                },
                {
                    key: '1',
                    label: 'Edit',
                    icon: 'pi pi-fw pi-pencil',
                    items: [
                        {
                            key: '1_0',
                            label: 'Left',
                            icon: 'pi pi-fw pi-align-left'
                        },
                        {
                            key: '1_1',
                            label: 'Right',
                            icon: 'pi pi-fw pi-align-right'
                        },
                        {
                            key: '1_2',
                            label: 'Center',
                            icon: 'pi pi-fw pi-align-center'
                        },
                        {
                            key: '1_3',
                            label: 'Justify',
                            icon: 'pi pi-fw pi-align-justify'
                        }
                    ]
                },
                {
                    key: '2',
                    label: 'Users',
                    icon: 'pi pi-fw pi-user',
                    items: [
                        {
                            key: '2_0',
                            label: 'New',
                            icon: 'pi pi-fw pi-user-plus'
                        },
                        {
                            key: '2_1',
                            label: 'Delete',
                            icon: 'pi pi-fw pi-user-minus'
                        },
                        {
                            key: '2_2',
                            label: 'Search',
                            icon: 'pi pi-fw pi-users',
                            items: [
                                {
                                    key: '2_2_0',
                                    label: 'Filter',
                                    icon: 'pi pi-fw pi-filter',
                                    items: [
                                        {
                                            key: '2_2_0_0',
                                            label: 'Print',
                                            icon: 'pi pi-fw pi-print'
                                        }
                                    ]
                                },
                                {
                                    key: '2_2_1',
                                    icon: 'pi pi-fw pi-bars',
                                    label: 'List'
                                }
                            ]
                        }
                    ]
                },
                {
                    key: '3',
                    label: 'Events',
                    icon: 'pi pi-fw pi-calendar',
                    items: [
                        {
                            key: '3_0',
                            label: 'Edit',
                            icon: 'pi pi-fw pi-pencil',
                            items: [
                                {
                                    key: '3_0_0',
                                    label: 'Save',
                                    icon: 'pi pi-fw pi-calendar-plus'
                                },
                                {
                                    key: '3_0_0',
                                    label: 'Delete',
                                    icon: 'pi pi-fw pi-calendar-minus'
                                }
                            ]
                        },
                        {
                            key: '3_1',
                            label: 'Archive',
                            icon: 'pi pi-fw pi-calendar-times',
                            items: [
                                {
                                    key: '3_1_0',
                                    label: 'Remove',
                                    icon: 'pi pi-fw pi-calendar-minus'
                                }
                            ]
                        }
                    ]
                }
            ],
            code: {
                basic: `
<PanelMenu v-model:expandedKeys="expandedKeys" :model="items" />
`,
                options: `
<template>
    <div class="card flex flex-column align-items-center">
        <div class="mb-3">
            <Button type="button" icon="pi pi-plus" label="Expand All" @click="expandAll" class="mr-2" />
            <Button type="button" icon="pi pi-minus" label="Collapse All" @click="collapseAll" />
        </div>
        <PanelMenu v-model:expandedKeys="expandedKeys" :model="items" class="w-full md:w-25rem" />
    </div>
</template>

<script>
export default {
    data() {
        return {
            expandedKeys: {},
            items: [
                {
                    key: '0',
                    label: 'File',
                    icon: 'pi pi-fw pi-file',
                    items: [
                        {
                            key: '0_0',
                            label: 'New',
                            icon: 'pi pi-fw pi-plus',
                            items: [
                                {
                                    key: '0_0_0',
                                    label: 'Bookmark',
                                    icon: 'pi pi-fw pi-bookmark'
                                },
                                {
                                    key: '0_0_1',
                                    label: 'Video',
                                    icon: 'pi pi-fw pi-video'
                                }
                            ]
                        },
                        {
                            key: '0_1',
                            label: 'Delete',
                            icon: 'pi pi-fw pi-trash'
                        },
                        {
                            key: '0_2',
                            label: 'Export',
                            icon: 'pi pi-fw pi-external-link'
                        }
                    ]
                },
                {
                    key: '1',
                    label: 'Edit',
                    icon: 'pi pi-fw pi-pencil',
                    items: [
                        {
                            key: '1_0',
                            label: 'Left',
                            icon: 'pi pi-fw pi-align-left'
                        },
                        {
                            key: '1_1',
                            label: 'Right',
                            icon: 'pi pi-fw pi-align-right'
                        },
                        {
                            key: '1_2',
                            label: 'Center',
                            icon: 'pi pi-fw pi-align-center'
                        },
                        {
                            key: '1_3',
                            label: 'Justify',
                            icon: 'pi pi-fw pi-align-justify'
                        }
                    ]
                },
                {
                    key: '2',
                    label: 'Users',
                    icon: 'pi pi-fw pi-user',
                    items: [
                        {
                            key: '2_0',
                            label: 'New',
                            icon: 'pi pi-fw pi-user-plus'
                        },
                        {
                            key: '2_1',
                            label: 'Delete',
                            icon: 'pi pi-fw pi-user-minus'
                        },
                        {
                            key: '2_2',
                            label: 'Search',
                            icon: 'pi pi-fw pi-users',
                            items: [
                                {
                                    key: '2_2_0',
                                    label: 'Filter',
                                    icon: 'pi pi-fw pi-filter',
                                    items: [
                                        {
                                            key: '2_2_0_0',
                                            label: 'Print',
                                            icon: 'pi pi-fw pi-print'
                                        }
                                    ]
                                },
                                {
                                    key: '2_2_1',
                                    icon: 'pi pi-fw pi-bars',
                                    label: 'List'
                                }
                            ]
                        }
                    ]
                },
                {
                    key: '3',
                    label: 'Events',
                    icon: 'pi pi-fw pi-calendar',
                    items: [
                        {
                            key: '3_0',
                            label: 'Edit',
                            icon: 'pi pi-fw pi-pencil',
                            items: [
                                {
                                    key: '3_0_0',
                                    label: 'Save',
                                    icon: 'pi pi-fw pi-calendar-plus'
                                },
                                {
                                    key: '3_0_0',
                                    label: 'Delete',
                                    icon: 'pi pi-fw pi-calendar-minus'
                                }
                            ]
                        },
                        {
                            key: '3_1',
                            label: 'Archive',
                            icon: 'pi pi-fw pi-calendar-times',
                            items: [
                                {
                                    key: '3_1_0',
                                    label: 'Remove',
                                    icon: 'pi pi-fw pi-calendar-minus'
                                }
                            ]
                        }
                    ]
                }
            ]
        };
    },
    methods: {
        expandAll() {
            for (let node of this.items) {
                this.expandNode(node);
            }

            this.expandedKeys = {
                ...this.expandedKeys
            };
        },
        collapseAll() {
            this.expandedKeys = {};
        },
        expandNode(node) {
            if (node.items && node.items.length) {
                this.expandedKeys[node.key] = true;

                for (let child of node.items) {
                    this.expandNode(child);
                }
            }
        }
    }
};
<\/script>
`,
                composition: `
<template>
    <div class="card flex flex-column align-items-center">
        <div class="mb-3">
            <Button type="button" icon="pi pi-plus" label="Expand All" @click="expandAll" class="mr-2" />
            <Button type="button" icon="pi pi-minus" label="Collapse All" @click="collapseAll" />
        </div>
        <PanelMenu v-model:expandedKeys="expandedKeys" :model="items" class="w-full md:w-25rem"  />
    </div>
</template>

<script setup>
import { ref } from "vue";

const expandedKeys = ref({});
const items = ref([
    {
        key: '0',
        label: 'File',
        icon: 'pi pi-fw pi-file',
        items: [
            {
                key: '0_0',
                label: 'New',
                icon: 'pi pi-fw pi-plus',
                items: [
                    {
                        key: '0_0_0',
                        label: 'Bookmark',
                        icon: 'pi pi-fw pi-bookmark'
                    },
                    {
                        key: '0_0_1',
                        label: 'Video',
                        icon: 'pi pi-fw pi-video'
                    }
                ]
            },
            {
                key: '0_1',
                label: 'Delete',
                icon: 'pi pi-fw pi-trash'
            },
            {
                key: '0_2',
                label: 'Export',
                icon: 'pi pi-fw pi-external-link'
            }
        ]
    },
    {
        key: '1',
        label: 'Edit',
        icon: 'pi pi-fw pi-pencil',
        items: [
            {
                key: '1_0',
                label: 'Left',
                icon: 'pi pi-fw pi-align-left'
            },
            {
                key: '1_1',
                label: 'Right',
                icon: 'pi pi-fw pi-align-right'
            },
            {
                key: '1_2',
                label: 'Center',
                icon: 'pi pi-fw pi-align-center'
            },
            {
                key: '1_3',
                label: 'Justify',
                icon: 'pi pi-fw pi-align-justify'
            }
        ]
    },
    {
        key: '2',
        label: 'Users',
        icon: 'pi pi-fw pi-user',
        items: [
            {
                key: '2_0',
                label: 'New',
                icon: 'pi pi-fw pi-user-plus'
            },
            {
                key: '2_1',
                label: 'Delete',
                icon: 'pi pi-fw pi-user-minus'
            },
            {
                key: '2_2',
                label: 'Search',
                icon: 'pi pi-fw pi-users',
                items: [
                    {
                        key: '2_2_0',
                        label: 'Filter',
                        icon: 'pi pi-fw pi-filter',
                        items: [
                            {
                                key: '2_2_0_0',
                                label: 'Print',
                                icon: 'pi pi-fw pi-print'
                            }
                        ]
                    },
                    {
                        key: '2_2_1',
                        icon: 'pi pi-fw pi-bars',
                        label: 'List'
                    }
                ]
            }
        ]
    },
    {
        key: '3',
        label: 'Events',
        icon: 'pi pi-fw pi-calendar',
        items: [
            {
                key: '3_0',
                label: 'Edit',
                icon: 'pi pi-fw pi-pencil',
                items: [
                    {
                        key: '3_0_0',
                        label: 'Save',
                        icon: 'pi pi-fw pi-calendar-plus'
                    },
                    {
                        key: '3_0_0',
                        label: 'Delete',
                        icon: 'pi pi-fw pi-calendar-minus'
                    }
                ]
            },
            {
                key: '3_1',
                label: 'Archive',
                icon: 'pi pi-fw pi-calendar-times',
                items: [
                    {
                        key: '3_1_0',
                        label: 'Remove',
                        icon: 'pi pi-fw pi-calendar-minus'
                    }
                ]
            }
        ]
    }
]);


const expandAll = () => {
    for (let node of items.value) {
        expandNode(node);
    }

    expandedKeys.value = {...expandedKeys.value};
};

const collapseAll = () => {
    expandedKeys.value = {};
};

const expandNode = (node) => {
    if (node.items && node.items.length) {
        expandedKeys.value[node.key] = true;

        for (let child of node.items) {
            expandNode(child);
        }
    }
};
<\/script>
`
            }
        };
    },
    methods: {
        expandAll() {
            for (let node of this.items) {
                this.expandNode(node);
            }

            this.expandedKeys = {
                ...this.expandedKeys
            };
        },
        collapseAll() {
            this.expandedKeys = {};
        },
        expandNode(node) {
            if (node.items && node.items.length) {
                this.expandedKeys[node.key] = true;

                for (let child of node.items) {
                    this.expandNode(child);
                }
            }
        }
    }
};
</script>
