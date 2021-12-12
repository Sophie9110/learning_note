#### 1.php标记

  起始和结束标记，也就是 ` <?php     ?>`

 如果文件内容仅仅包含 PHP 代码，最好在文件末尾删除 PHP 结束标记。这可以避免在 PHP 结束标记之后万一意外加入了空格或者换行符，会导致 PHP 开始输出这些空白，而脚本中此时并无输出的意图。

``<?php`
`echo "Hello world";`

`// ... 更多代码`

`echo "Last statement";`

`// 脚本在此处结束，没有 PHP 结束标记``



#### 2.html 表单

`<form action="index.php" method="post">`

   `Enter your name:` 

   `<input type="text" name="name">`

​    `<input  type ="submit">`

​    `</form>`

其对应PHP：

 ``  <?php` 

​    `$name = $_POST["name"];`

   `echo "hello," . $name ;`

``?>``

#### 3.数组

`$peaple =array("Bob","Sophie");`

   `$numbers=array(3,6,9);`

   `$sum=0;`

   `foreach($peaple as $person){`

​     `echo $person . " " ;`

   `}`

   `foreach($numbers as $number){`

​    `$sum=$sum+$number;`

   `}`

   `echo $sum;`

``   

`?>`



对应教程：Learn PHP in 15 minutes https://www.youtube.com/watch?v=ZdP0KM49IVk



