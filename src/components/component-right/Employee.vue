<template>
  <div class="content-body">
    <div
      class="grid grid-employee el-table el-table--fit el-table--scrollable-y el-table--enable-row-hover el-table--enable-row-transition"
    >
      <table
        id="tbListData"
        cellspacing="0"
        cellpadding="0"
        border="0"
        class="el-table__body"
        style="min-width: 100%"
      >
        <thead class="has-gutter">
          <tr class="el-table__row">
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_114 is-leaf"
              fieldName="EmployeeCode"
            >
              <div class="cell">Mã nhân viên</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_115 is-leaf"
              fieldName="FullName"
            >
              <div class="cell">Họ và tên</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_116 is-leaf"
              fieldName="GenderName"
            >
              <div class="cell">Giới tính</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_116 is-leaf"
              fieldName="DateOfBirth"
              formatType="ddmmyyyy"
              style="text-align: center"
            >
              <div class="cell">Ngày sinh</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_116 is-leaf"
              fieldName="PhoneNumber"
            >
              <div class="cell">Điện thoại</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_116 is-leaf"
              fieldName="Email"
            >
              <div class="cell">Email</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_116 is-leaf"
              fieldName="PositionName"
            >
              <div class="cell">Chức vụ</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_116 is-leaf"
              fieldName="DepartmentName"
            >
              <div class="cell">Phòng ban</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_116 is-leaf"
              fieldName="Salary"
              formatType="Money"
            >
              <div class="cell" style="text-align: right">Mức lương cơ bản</div>
            </th>
            <th
              colspan="1"
              rowspan="1"
              class="el-table_30_column_116 is-leaf"
              fieldName="WorkStatusName"
            >
              <div class="cell">Tình trạng công việc</div>
            </th>
            <th class="gutter" style="width: 6px"></th>
          </tr>
        </thead>
        <tbody>
          <tr
            class="el-table__row"
            v-for="employee in employees"
            :key="employee.EmployeeId"
            @dblclick="rowOnClick(employee)"
          >
            <td>
              <div class="cell">{{ employee.EmployeeCode }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.FullName }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.GenderName }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.DateOfBirth }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.PhoneNumber }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.Email }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.PositionName }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.DepartmentName }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.Salary }}</div>
            </td>
            <td>
              <div class="cell">{{ employee.WorkStatusName }}</div>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <div class="paging-bar">
      <div class="paging-record-info">Hiển thị <b>1-10/1000</b> nhân viên</div>
      <div class="paging-option">
        <div class="btn-select-page m-btn-firstpage"></div>
        <div class="btn-select-page m-btn-prev-page"></div>
        <div class="m-btn-list-page">
          <button class="btn-pagenumber btn-pagenumber-selected">1</button>
          <button class="btn-pagenumber">2</button>
          <button class="btn-pagenumber">3</button>
          <button class="btn-pagenumber">4</button>
        </div>
        <div class="btn-select-page m-btn-next-page"></div>
        <div class="btn-select-page m-btn-lastpage"></div>
      </div>
      <div class="paging-record-option"><b>10</b> nhân viên/trang</div>
    </div>
    <FormAdd @closePopup="closePopup" :isHide="isHideParent" />
  </div>
</template>
<script>

import FormAdd from './FormAdd.vue'
export default {
  name: "Employees",
  components: {
    FormAdd,

  },
  methods: {
    btnAddOnClick() {
      this.isHideParent = false;
    },
    rowOnClick(employee) {
      alert(employee.FullName);
    },
    closePopup(value) {
      this.isHideParent = value;
    },
  },
  data() {
    return {
      color: "#019160",
      width: 50,
      height: 50,
      backgroundColor: "#000",
      fullPage: false,
      opacity: 0.2,
      isHideParent: true,
      blur: "15px",
    };
  },

};
</script>

<style scoped>

/*pagging */
.filter-bar {
    width: 100%;
    display: flex;
    align-items: center;
    height: 40px;
}

    .filter-bar .filter-right {
        position:absolute;
        right: 16px;
    }

.paging-bar {
    border-top: 2px solid #bbbbbb;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0 16px;
    z-index: 1 !important;
}
    .paging-bar .paging-record-info {
        position: absolute;
        left: 16px;
    }

    .paging-bar .paging-record-option {
        position: absolute;
        right: 16px;
    }

    .paging-bar .paging-option button{
        outline: none;
        cursor: pointer;
    }
    .paging-bar .paging-option{
        display: flex;
    }
/* Grid */
.grid {
    width: 100%;
    overflow-x:auto;
    overflow-y:hidden;
}


    .grid .grid-header {
        height: 50px;
    }

    .grid .grid-content, .tablescroll_wrapper, .tablescroll {
        height: calc(100% - 25px);
    }


.grid table th {
    border-bottom: 1px solid #bbbbbb;
    /*border-left: 1px solid #bbbbbb;*/
    /*padding: 10px 16px !important;*/
    text-align: left;
}

    .grid table th .cell {
        padding: 15px 16px !important;
    }

.grid table td {
    border-bottom: 1px solid #bbbbbb;
    /*border-left: 1px solid #bbbbbb;*/
    padding: 15px 16px !important;
    text-align: left;
    white-space: nowrap;
    box-sizing: border-box;
    overflow: hidden;
    text-overflow: ellipsis;
    word-break: break-all;
}


.grid table th {
    /*z-index:1;
    position:sticky;
    background-color: #ffffff;
    top:0px;
    left:0;
    padding-top: 22px !important;*/
    font-weight: bold !important;
}

.grid tbody tr:nth-child(2n+1) {
    background-color: #fafafa;
}

.grid tbody tr:hover {
    background-color: #d9d9d9;
    cursor: pointer;
}

.grid table td span {
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}

/*define height and width of scrollable area. Add 16px to width for scrollbar*/
div.tableContainer {
    clear: both;
    border: 1px solid #963;
    height: 285px;
    overflow: auto;
    width: 900px;
}
/*Reset overflow value to hidden for all non-IE browsers.*/
html > body div.tableContainer {
    overflow: hidden;
    width: 900px;
}
    /*define width of table. IE browsers only*/
    div.tableContainer table {
        float: left;
        border-spacing: 0;
    }

        div.tableContainer table tr {
            display: table;
            width: 100%;
        }
/* set table header to a fixed position. WinIE 6.x only                                       
 In WinIE 6.x, any element with a position property set to relative and is a child of       
 an element that has an overflow property set, the relative value translates into fixed.    
 Ex: parent element DIV with a class of tableContainer has an overflow property set to auto */
thead.fixedHeader tr {
    position: relative;
}
/* set THEAD element to have block level attributes. All other non-IE browsers            
 this enables overflow to work on TBODY element. All other non-IE, non-Mozilla browsers 
 make the TH elements pretty */
.grid thead.fixedHeader th {
    border: 1px solid #ccc;
    font-weight: normal;
    text-align: left;
}

html > body .grid thead.fixedHeader {
    display: table;
    overflow: auto;
    width: 100%;
}

html > body .grid tbody.scrollContent {
    display: block;
    height: 262px;
    overflow: auto;
    width: 100%;
}
    /*make TD elements pretty. Provide alternating classes for striping the table*/
    .grid  tbody.scrollContent td, tbody.scrollContent tr.normalRow td {
        background: #fff;
        border-bottom: none;
        border-left: none;
        border-right: 1px solid #ccc;
        border-top: 1px solid #ddd;
    }

.grid td div {
    max-width: 200px;
    white-space: nowrap;
    box-sizing: border-box;
    overflow: hidden;
    text-overflow: ellipsis;
    word-break: break-all;
}

.grid-employee {
  margin-top: 10px;
  height: calc(100vh - 234px);
}

.el-avatar-employee {
  padding-top: 16px;
  padding-right: 16px;
}

.el-left {
  width: calc(100% - 180px);
}

.el-avatar-employee .el-avatar {
  border: 1px solid #ccc;
  width: 160px;
  height: 160px;
  margin: 0 auto;
  border-radius: 50%;
  cursor: pointer;
  /* background-image: url("/assets/img/default-avatar.jpg"); */
  background-repeat: no-repeat;
  background-position: center;
  background-size: cover;
}

.el-avatar-note {
  font-size: 12px;
}
.filter-left {
  display: flex;
}
.filter-left select {
  margin-left: 10px;
  margin-right: 10px;
}

.currency-for-input {
  position: absolute;
  right: 40px;
  line-height: 40px;
  font-style: italic;
}

#txtSearchEmployee {
  min-width: 300px;
}
</style>