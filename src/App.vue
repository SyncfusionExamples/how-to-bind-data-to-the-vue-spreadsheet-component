<script>
  import { SpreadsheetComponent, SheetsDirective, SheetDirective,
      RangesDirective, RangeDirective, ColumnsDirective,
      ColumnDirective, RowsDirective, RowDirective, CellsDirective,
      CellDirective, getFormatFromType } from '@syncfusion/ej2-vue-spreadsheet';
  import { DataManager, WebApiAdaptor } from '@syncfusion/ej2-data'; // Remote data binding
  import {defaultData} from './default.json'; // Local data binding
  import {ButtonComponent} from '@syncfusion/ej2-vue-buttons';
  export default{
    components: {
      'ejs-spreadsheet': SpreadsheetComponent,
      'e-sheets': SheetsDirective,
      'e-sheet': SheetDirective,
      'e-ranges': RangesDirective,
      'e-range': RangeDirective,
      'e-columns': ColumnsDirective,
      'e-column': ColumnDirective,
      'e-rows': RowsDirective,
      'e-row': RowDirective,
      'e-cells': CellsDirective,
      'e-cell': CellDirective,
      'ejs-button': ButtonComponent
    },
    data(){
      return{
        // data: new DataManager({
        //             // Remote service url
        //             url: "https://services.syncfusion.com/vue/production/api/Orders",
        //             adaptor: new CustomAdaptor(),
        //             crossDomain: true,
        //         }),
        customWidth: 130,
        currencyFormat: getFormatFromType("Currency")
      }
    },
    methods: {
      created: function() {
        var spreadsheet = this.$refs.spreadsheet;
        spreadsheet.cellFormat({ fontWeight: 'bold', textAlign: 'center' }, 'A1:F1');
      },
      // btnClk: function(){
      //   this.$refs.spreadsheet.ej2Instances.sheets[0].ranges[0].dataSource = defaultData;
      // }
    }
  }
</script>

<template>
  <div>
    <!-- <ejs-button v-on:click="btnClk" style="margin: 5px;">Load Data</ejs-button> -->
    <!-- <e-ranges> // Add inside e-sheets to render remote data
            <e-range :dataSource="data"></e-range>
          </e-ranges> -->
    <ejs-spreadsheet ref="spreadsheet" :created="created">
      <e-sheets>
        <e-sheet name="Monthly Budget">
          <e-rows>
            <e-row>
                <e-cells>
                    <e-cell value="Category"></e-cell>
                    <e-cell value="Planned cost"></e-cell>
                    <e-cell value="Actual cost"></e-cell>
                </e-cells>
            </e-row>
            <e-row>
                <e-cells>
                    <e-cell value="Food"></e-cell>
                    <e-cell value="$7000"></e-cell>
                    <e-cell value="$8120"></e-cell>
                </e-cells>
            </e-row>
            <e-row>
                <e-cells>
                    <e-cell value="Loan"></e-cell>
                    <e-cell value="$1500"></e-cell>
                    <e-cell value="$1500"></e-cell>
                </e-cells>
            </e-row>
            <e-row>
                <e-cells>
                    <e-cell value="Medical"></e-cell>
                    <e-cell value="$300"></e-cell>
                    <e-cell value="$0"></e-cell>
                </e-cells>
            </e-row>
            <e-row>
                <e-cells>
                    <e-cell value="Clothing"></e-cell>
                    <e-cell value="$400"></e-cell>
                    <e-cell value="$140"></e-cell>
                </e-cells>
            </e-row>
            <e-row>
                <e-cells>
                    <e-cell value="Education"></e-cell>
                    <e-cell value="$900"></e-cell>
                    <e-cell value="$750"></e-cell>
                </e-cells>
            </e-row>
            <e-row>
                <e-cells>
                    <e-cell value="Insurance"></e-cell>
                    <e-cell value="$30"></e-cell>
                    <e-cell value="$30"></e-cell>
                </e-cells>
            </e-row>
          </e-rows> 
          <e-columns>
            <e-column :width="customWidth"></e-column>
            <e-column :width="customWidth"></e-column>
            <e-column :width="customWidth"></e-column>
            <e-column :width="customWidth"></e-column>
            <e-column :width="customWidth"></e-column>
            <e-column :width="customWidth"></e-column>
          </e-columns> 
        </e-sheet>
      </e-sheets>
    </ejs-spreadsheet>
  </div>
</template>

<style>
  @import "../node_modules/@syncfusion/ej2-base/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-buttons/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-dropdowns/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-inputs/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-navigations/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-popups/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-splitbuttons/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-grids/styles/material.css";
  @import "../node_modules/@syncfusion/ej2-vue-spreadsheet/styles/material.css";
</style>
