# NotePad
              期中实验
              基本功能一：NoteList中显示条目增加时间戳
              (https://github.com/WYF-se/NotePad-master/时间戳.png)
              时间戳所用技术与源码 
              其中更改了PROJECTION的具体参数：增加了修改时间的变量
```
private static final String[] PROJECTION = new String[] {

       	 NotePad.Notes._ID, // 0
       	 NotePad.Notes.COLUMN_NAME_TITLE, // 1
       	 NotePad.Notes.COLUMN_NAME_MODIFICATION_DATE,
       	 //NotePad.Notes.FLAG,
  };
  ```
              利用Cursor查询到数据库的具体内容然后利用SimpleAdapter显示在页面上
```
Cursor cursor = managedQuery(
            getIntent().getData(),            // Use the default content URI for the provider.
            PROJECTION,                       // Return the note ID and title for each note.
            null,                             // No where clause, return all records.
            null,                             // No where clause, therefore no where column values.
            NotePad.Notes.DEFAULT_SORT_ORDER  // Use the default sort order.
    );
    // The names of the cursor columns to display in the view, initialized to the title column
    String[] dataColumns = {  NotePad.Notes.COLUMN_NAME_TITLE , NotePad.Notes.COLUMN_NAME_MODIFICATION_DATE} ;
    int[] viewIDs = { android.R.id.list_item_customize_title_text_view,android.R.id.list_item_customize_date_text_view};
    SimpleCursorAdapter adapter
            = new SimpleCursorAdapter(
            this,                             // The Context for the ListView
            R.layout.noteslist_item,          // Points to the XML for a list item
            cursor,                           // The cursor to get items from
            dataColumns,
            viewIDs
    );
    // Sets the ListView's adapter to be the cursor adapter that was just created.
    setListAdapter(adapter);
    ```
               实验二
