# Lesson-5
Лабораторная работа №5
Создание функции отрисовки таблицы умножения. 
	<?php
       function drawTable($cols = 10, $rows = 10, $color = 'brown') {
	     echo "<table border = '1' width='500' text-align:center>";
	     for ($tr = 1; $tr <= $rows; $tr++) { 
	     echo "<tr>"; //
	      for ($td = 1; $td <= $cols; $td++) { 
	            if ($tr == 1 || $td == 1) {
	               echo "<th style = 'background : {$color}'>" . $tr * $td . "</th>"; // <th> - заголовочные ячейки
	            } else
	     echo "<td>" . $tr * $td . "</td>"; // $tr * $td - для вывода значений (цифр) внутри таблицы
	        	}
	        }
	 echo "</tr>";
	 echo "</table>";
	}
?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="ru" lang="ru">
	<head>
		<title>Таблица умножения</title>
		<meta http-equiv="content-type"
			content="text/html; charset=utf-8" />
		<link rel="stylesheet" type="text/css" href="style.css" />
	</head>
	<body>
   		<div id="header">
			<!-- Верхняя часть страницы -->
			<img src="logo.gif" width="187" height="29" alt="Наш логотип" class="logo" />
			<span class="slogan">приходите к нам учиться</span>
			<!-- Верхняя часть страницы -->
		</div>
			<div id="content">
			<!-- Заголовок -->
			<h1>Таблица умножения</h1>
			<!-- Заголовок -->
			<!-- Область основного контента -->
			<form action=''>
				<label>Количество колонок: </label><br />
				<input name='cols' type='text' value="" /><br />
				<label>Количество строк: </label><br />
				<input name='rows' type='text' value="" /><br />
				<label>Цвет: </label><br />
				<input name='color' type='text' value="" /><br /><br />
				<input type='submit' value='Создать' />
				</form>
			 <!-- Таблица -->
				 <?php
         drawTable($cols,$rows,$color);{
         }
         ?> 
			 <!-- Таблица -->
			<!-- Область основного контента -->
		    </div>
		    <div id="nav">
					<h2>Навигация по сайту</h2>     
			<!-- Меню -->
			<ul>
				<li><a href='index.php'>Домой</a></li>
				<li><a href='about.php'>О нас</a></li>
				<li><a href='contact.php'>Контакты</a></li>
				<li><a href='table.php'>Таблица умножения</a></li>
				<li><a href='calc.php'>Калькулятор</a></li>
			</ul>
			<!-- Меню -->
		</div>
		<div id="footer">
			<!-- Нижняя часть страницы -->
			&copy; Copyright, 2017 - 2018
			<!-- Нижняя часть страницы -->
		</div>
	</body>
</html>
Лабораторная работа №5.2
Создание функции отрисовки меню навигации по сайту
