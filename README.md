# Hartford Crashes

Interactive heatmap of car crashes in Hartford between 2015 and 2020 which
displays pre-processed data from [UConn Crash Data Repository](https://www.ctcrash.uconn.edu/).
It can be adapted for other towns in Connecticut, or other states that have similar data.

![Heatmap gif](./img/demo.gif)

## Pre-process data

1. Navigate to https://www.ctcrash.uconn.edu/ and create an account if you don't have one yet.
2. Log in, and go to `Data Query Tool`.
3. Select a `MMUCC(2015-)` dataset, specify dates and town (or multiple towns).
4. Run the query, and then click `Export To CSV` button above the interactive table. A link will be sent to your email account to download the archive. Note that the tool may prevent you from exporting datasets that are "too large". In that case, break down your query (for example, instead of downloading 2015-2020 data, do 2015-2018
as one export, and 2019-2020 as another).
5. Unzip the archive(s), and put them inside `data/` folder.
6. Open `ProcessCrashes.ipynb` notebook, and add your export IDs (numbers) to the `exports` list.
7. Run the notebook. This should generate a CSV (`crashes.csv`) and a JSON file (`crashes.json`) with relevant data.

## Modify map's appearance

This map is fully front-end, and loads data once from the CSV file using PapaParse JS library. You
can change it to fetch the JSON file using `$.getJSON()` function of jQuery, although it is slightly
heavier than the CSV. Modify `index.html` to set custom map title, and `script.js` to change initial coordinates, date ranges, and anything else related to the map really.

## I still have questions

Get in touch with ilya@picturedigits.com if you have any other questions or suggestions!

## License
MIT
