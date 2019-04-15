---
layout: index
---
My career began in London designing Flash and 3D animation, and I’ve arrived as a full stack develeoper working in London & California.

I wonder what’s next...



| Attribute                       | Element          | Type               | Description |
| :------------------------------ | :---------------------------- | :------------------------------ | :------------------------- |
| `mdDesc`       | `mdColumn` | `[expression]` | If present, the column will sort descending first. The default is to sort ascending first. |
| `mdOnReorder`  | `mdHead`   | `function`     | A callback function for when the order changes. The callback will receive the new order. |
| `mdOrder`      | `mdHead`   | `string`       | A variable to bind the sort order to. |
| `mdOrderBy`    | `mdColumn` | `string`       | The value to bind to the sort order. |


<md-table-container>
          <table md-table md-row-select ng-model="selected" md-progress="promise">
            <thead fix-head md-head md-order="query.order">
              <tr md-row>
                <th md-column md-order-by="name"><span>Dessert (100g serving)</span></th>
                <th md-column md-order-by="type"><span>Type</span></th>
                <th md-column md-numeric md-order-by="calories.value" md-desc><span>Calories</span></th>
                <th md-column md-numeric md-order-by="fat.value"><span>Fat (g)</span></th>
                <th md-column md-numeric md-order-by="carbs.value"><span>Carbs (g)</span></th>
                <th md-column md-numeric md-order-by="protein.value"><span>Protein (g)</span></th>
                <th md-column md-numeric md-order-by="sodium.value" hide-gt-xs show-gt-md><span>Sodium (mg)</span></th>
                <th md-column md-numeric md-order-by="calcium.value" hide-gt-xs show-gt-lg><span>Calcium (%)</span></th>
                <th md-column md-numeric md-order-by="iron.value" hide-gt-xs show-gt-lg><span>Iron (%)</span></th>
              </tr>
            </thead>
            <tbody md-body>
              <tr md-row md-select="dessert" md-auto-select ng-repeat="dessert in desserts.data | filter: filter.search | orderBy: query.order | limitTo: query.limit : (query.page -1) * query.limit">
                <td md-cell>{{dessert.name}}</td>
                <td md-cell>
                  <md-select ng-model="dessert.type" placeholder="Other">
                    <md-option ng-value="type" ng-repeat="type in getTypes()">{{type}}</md-option>
                  </md-select>
                </td>
                <td md-cell>{{dessert.calories.value}}</td>
                <td md-cell>{{dessert.fat.value | number: 2}}</td>
                <td md-cell>{{dessert.carbs.value}}</td>
                <td md-cell>{{dessert.protein.value | number: 2}}</td>
                <td md-cell hide-gt-xs show-gt-md>{{dessert.sodium.value}}</td>
                <td md-cell hide-gt-xs show-gt-lg>{{dessert.calcium.value}}%</td>
                <td md-cell hide-gt-xs show-gt-lg>{{dessert.iron.value}}%</td>
                
              </tr>
            </tbody>
          </table>
        </md-table-container>

