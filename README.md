# dynamic-mini-table

A flexible, customizable React table component for dynamic data display, sorting, filtering, searching, pagination, and drag-and-drop row reordering.

---

## Installation

```bash
npm install dynamic-mini-table
# or
yarn add dynamic-mini-table
```

---

## Usage

```tsx
import TableView from "dynamic-mini-table";

const headers = [
  { key: "id", title: "ID", width: 80, sort: true },
  { key: "name", title: "Name", width: 200 },
  // ...more columns
];

const dataSource = [
  { id: 1, name: "Alice", email: "alice@email.com" },
  { id: 2, name: "Bob", email: "bob@email.com" },
  // ...more rows
];

<TableView
  headers={headers}
  dataSource={dataSource}
  pagination={true}
  filter={true}
  search={true}
  showMove={true}
  onUpdateOrder={({ orderRows, newOrder }) => {
    // handle new order
  }}
/>;
```

---

## Props

Below are the **public props** you can use with `<TableView />`.  
Some fields in the code are for internal/configuration use and are not intended as direct props—these are marked as **(internal)**.
| Prop | Type | Default | Description |
| --------------------- | ------------------------------------ | ------------ | ----------------------------------------------------------------------- |
| `headers` | `Header[]` | **Required** | Array of column definitions (see Header Definition below). |
| `dataSource` | `SourceData[]` | **Required** | Array of data objects for each row. |
| `selectedRows` | `SourceData[]` | `[]` | Array of currently selected row objects. |
| `onRowSelect` | `(rows) => void` | `() => {}` | Callback when row selection changes. |
| `showMove` | `boolean` | `false` | Enable drag-and-drop row reordering. |
| `onUpdateOrder` | `({orderRows, newOrder}) => void` | `() => {}` | Callback when row order changes. Receives new order and reordered rows. |
| `pagination` | `boolean` | `true` | Enable pagination controls. |
| `paginationPlacement` | `"center" \| "left" \| "right"` | `"right"` | Placement of pagination controls. |
| `paginationType` | `"default" \| "inList"` | `"default"` | Pagination mode. |
| `pageOptions` | `number[]` | `[10,25,50]` | Available page size options. |
| `filter` | `boolean` | `true` | Enable filter dropdown. |
| `filterLabel` | `string` | `"Filter"` | Label for the filter dropdown. |
| `filterList` | `filterItem[]` | `[]` | List of filter options. |
| `filterValue` | `string \| number` | `""` | Currently selected filter value. |
| `onFilterSelect` | `(value, item) => void` | `() => {}` | Callback when a filter is selected. |
| `filterView` | `React.ReactElement` | | Custom filter component. |
| `search` | `boolean` | `true` | Enable search input. |
| `searchData` | `string` | | Search query string. |
| `onSearch` | `(value) => void` | `() => {}` | Callback when a search is performed. |
| `searchView` | `React.ReactElement` | | Custom search component. |
| `searchInstant` | `boolean` | `false` | If true, search triggers on input change. |
| `searchType` | `"default" \| "trigger" \| "expand"` | `"default"` | Search input type. |
| `searchMode` | `"default" \| "inline"` | `"default"` | Search mode. |
| `searchKeys` | `string[]` | `[]` | Keys to search in each row object. |
| `searchTrigger` | `"click" \| "hover"` | `"click"` | How search is triggered. |
| `searchFieldClass` | `string` | | Custom class for search field. |
| `check` | `boolean` | `true` | Show checkbox for row selection. |
| `selectMatchKey` | `string` | `"id"` | Unique key in data objects for selection and ordering. |
| `tableType` | `"default" \| "striped"` | `"default"` | Table style variant. |
| `tableClass` | `string` | | Additional class for table container. |
| `tableHeaderClass` | `string` | | Additional class for table header. |
| `headerType` | `"default" \| "stick"` | `"stick"` | Table header style variant. |
| `start_stick` | `boolean` | `true` | Stick first column (frozen left). |
| `end_stick` | `boolean` | `true` | Stick last column (frozen right). |
| `clampColumnMessage` | `string` | | Message to show when column content is clamped. |
| `globalPlacement` | `"center" \| "left" \| "right"` | `"center"` | Default column alignment. |
| `loading` | `boolean` | `false` | Show loading state. |
| `loadRender` | `React.ReactElement` | | Custom loader component. |
| `loaderClass` | `string` | | Loader CSS class. |

### Internal/Advanced Fields (not typical props)

`wrapper_class`, `action_container`, `custom_pre_action_start`, `custom_post_action_start`, `custom_pre_action_end`, `custom_post_action_end`, `action_container_start_class`, `action_container_end_class`, `action__container_start_action_icon`, `action_container_start_action_label`, `action__container_start_action_class`, `enableAction`, `handleActionClick`, etc.

> **Note:** These are for advanced customization and are not required for most use cases.

---

## Header Definition

Each header object can have:

| Property    | Type                            | Default     | Description                                |
| ----------- | ------------------------------- | ----------- | ------------------------------------------ |
| `key`       | `string`                        |             | Data key for the column (required).        |
| `title`     | `string`                        |             | Column title (required).                   |
| `width`     | `number`                        |             | Column width in pixels.                    |
| `minWidth`  | `number`                        |             | Minimum column width.                      |
| `maxWidth`  | `number`                        |             | Maximum column width.                      |
| `sort`      | `boolean`                       | `false`     | Enable sorting for this column.            |
| `type`      | `"default" \| "html"`           | `"default"` | Cell type, e.g., `'html'` for raw HTML.    |
| `expand`    | `boolean`                       | `false`     | Enable expandable row for this column.     |
| `viewLines` | `number`                        |             | Clamp lines for cell content (multi-line). |
| `placement` | `"left" \| "center" \| "right"` | `"center"`  | Text alignment.                            |

<!-- --- -->

<!--
## Types

See [`src/Components/Util/Interface.ts`](../src/Components/Util/Interface.ts) for full TypeScript interfaces. -->

---

## License

MIT

---

**Note:**  
If you need advanced customization, please contact directly -[email me](mailto:rakibhssn10025@gmail.com). Feel free to contact us.
