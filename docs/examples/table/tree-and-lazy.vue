<template>
  <div>
    <el-table
      :data="tableData"
      style="width: 100%; margin-bottom: 20px"
      row-key="id"
      border
      default-expand-all
    >
      <el-table-column prop="name" label="name" sortable />
      <el-table-column prop="type" label="type" sortable />
      <el-table-column prop="url" label="url" sortable />
      <el-table-column prop="intro" label="intro" sortable />
      <el-table-column prop="createdAt" label="createdAt" sortable />
      <el-table-column parentId="updatedAt" label="updatedAt" sortable />
    </el-table>

    <el-table
      :data="tableData1"
      style="width: 100%"
      row-key="id"
      border
      lazy
      :load="load"
      :tree-props="{ children: 'children', hasChildren: 'hasChildren' }"
    >
      <el-table-column prop="date" label="Date" />
      <el-table-column prop="name" label="Name" />
      <el-table-column prop="address" label="Address" />
    </el-table>
  </div>
</template>

<script lang="ts" setup>
interface User {
  id: number
  date: string
  name: string
  address: string
  hasChildren?: boolean
  children?: User[]
}

const load = (
  row: User,
  treeNode: unknown,
  resolve: (data: User[]) => void
) => {
  setTimeout(() => {
    resolve([
      {
        id: 31,
        date: '2016-05-01',
        name: 'wangxiaohu',
        address: 'No. 189, Grove St, Los Angeles',
      },
      {
        id: 32,
        date: '2016-05-01',
        name: 'wangxiaohu',
        address: 'No. 189, Grove St, Los Angeles',
      },
    ])
  }, 1000)
}

const tableData: User[] = [
        {
            "id": 1,
            "name": "系统总览",
            "type": 1,
            "url": "/main/analysis",
            "icon": "el-icon-menu",
            "sort": 1,
            "intro": null,
            "parentId": null,
            "createdAt": "2025-03-28T20:19:42",
            "updatedAt": "2025-03-29T00:31:40",
            "children": [
                {
                    "id": 9,
                    "name": "系统中心",
                    "type": 2,
                    "url": "/main/analysis/system",
                    "icon": "el-icon-data-analysis",
                    "sort": 5,
                    "intro": null,
                    "parentId": 1,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": []
                },
                {
                    "id": 10,
                    "name": "商品统计",
                    "type": 2,
                    "url": "/main/analysis/product",
                    "icon": "el-icon-data-chart",
                    "sort": 6,
                    "intro": null,
                    "parentId": 1,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": []
                }
            ]
        },
        {
            "id": 2,
            "name": "系统管理",
            "type": 1,
            "url": "/main/system",
            "icon": "el-icon-setting",
            "sort": 2,
            "intro": null,
            "parentId": null,
            "createdAt": "2025-03-28T20:19:42",
            "updatedAt": "2025-03-29T00:31:40",
            "children": [
                {
                    "id": 11,
                    "name": "用户管理",
                    "type": 2,
                    "url": "/main/system/user",
                    "icon": "el-icon-user",
                    "sort": 7,
                    "intro": null,
                    "parentId": 2,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": [
                        {
                            "id": 18,
                            "name": "创建用户",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.user.create",
                            "parentId": 11,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:45",
                            "children": []
                        },
                        {
                            "id": 19,
                            "name": "删除用户",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.user.delete",
                            "parentId": 11,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:47",
                            "children": []
                        },
                        {
                            "id": 20,
                            "name": "修改用户",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.user.update",
                            "parentId": 11,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:48",
                            "children": []
                        },
                        {
                            "id": 21,
                            "name": "查询用户",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.user.query",
                            "parentId": 11,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:50",
                            "children": []
                        }
                    ]
                },
                {
                    "id": 12,
                    "name": "部门管理",
                    "type": 2,
                    "url": "/main/system/department",
                    "icon": "el-icon-office-building",
                    "sort": 8,
                    "intro": null,
                    "parentId": 2,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": [
                        {
                            "id": 22,
                            "name": "创建部门",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.department.create",
                            "parentId": 12,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:51",
                            "children": []
                        },
                        {
                            "id": 23,
                            "name": "删除部门",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.department.delete",
                            "parentId": 12,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:52",
                            "children": []
                        },
                        {
                            "id": 24,
                            "name": "修改部门",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.department.update",
                            "parentId": 12,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:52",
                            "children": []
                        },
                        {
                            "id": 25,
                            "name": "查询部门",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.department.query",
                            "parentId": 12,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:54",
                            "children": []
                        }
                    ]
                },
                {
                    "id": 13,
                    "name": "角色管理",
                    "type": 2,
                    "url": "/main/system/role",
                    "icon": "el-icon-permission",
                    "sort": 9,
                    "intro": null,
                    "parentId": 2,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": [
                        {
                            "id": 26,
                            "name": "创建角色",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.role.create",
                            "parentId": 13,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:58",
                            "children": []
                        },
                        {
                            "id": 27,
                            "name": "删除角色",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.role.delete",
                            "parentId": 13,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:58",
                            "children": []
                        },
                        {
                            "id": 28,
                            "name": "修改角色",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.role.update",
                            "parentId": 13,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:15:59",
                            "children": []
                        },
                        {
                            "id": 29,
                            "name": "查询角色",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.role.query",
                            "parentId": 13,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:16:02",
                            "children": []
                        }
                    ]
                },
                {
                    "id": 14,
                    "name": "菜单管理",
                    "type": 2,
                    "url": "/main/system/menu",
                    "icon": "el-icon-menu",
                    "sort": 10,
                    "intro": null,
                    "parentId": 2,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": [
                        {
                            "id": 30,
                            "name": "创建菜单",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.menu.create",
                            "parentId": 14,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:16:29",
                            "children": []
                        },
                        {
                            "id": 31,
                            "name": "删除菜单",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.menu.delete",
                            "parentId": 14,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:16:30",
                            "children": []
                        },
                        {
                            "id": 32,
                            "name": "修改菜单",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.menu.update",
                            "parentId": 14,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:16:32",
                            "children": []
                        },
                        {
                            "id": 33,
                            "name": "查询菜单",
                            "type": 3,
                            "url": null,
                            "icon": null,
                            "sort": null,
                            "intro": "system.menu.query",
                            "parentId": 14,
                            "createdAt": "2025-03-28T20:40:21",
                            "updatedAt": "2025-03-28T23:16:34",
                            "children": []
                        }
                    ]
                }
            ]
        },
        {
            "id": 3,
            "name": "商品中心",
            "type": 1,
            "url": "/main/product",
            "icon": "el-icon-shopping-cart",
            "sort": 3,
            "intro": null,
            "parentId": null,
            "createdAt": "2025-03-28T20:19:42",
            "updatedAt": "2025-03-29T00:31:40",
            "children": [
                {
                    "id": 15,
                    "name": "商品类别",
                    "type": 2,
                    "url": "/main/product/category",
                    "icon": "el-icon-folder",
                    "sort": 11,
                    "intro": null,
                    "parentId": 3,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": []
                },
                {
                    "id": 16,
                    "name": "商品信息",
                    "type": 2,
                    "url": "/main/product/item",
                    "icon": "el-icon-document",
                    "sort": 12,
                    "intro": null,
                    "parentId": 3,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": []
                }
            ]
        },
        {
            "id": 4,
            "name": "随便聊聊",
            "type": 1,
            "url": "/main/story",
            "icon": "el-icon-chat",
            "sort": 4,
            "intro": null,
            "parentId": null,
            "createdAt": "2025-03-28T20:19:42",
            "updatedAt": "2025-03-29T00:31:40",
            "children": [
                {
                    "id": 17,
                    "name": "我的故事",
                    "type": 2,
                    "url": "/main/story/my-story",
                    "icon": "el-icon-edit",
                    "sort": 13,
                    "intro": null,
                    "parentId": 4,
                    "createdAt": "2025-03-28T20:28:36",
                    "updatedAt": "2025-03-29T00:31:40",
                    "children": []
                }
            ]
        }
    ]
</script>
