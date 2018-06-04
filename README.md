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
