# Lesson-5
Лабораторная работа №5
Создание функции отрисовки таблицы умножения. 
<?php
function getTable($cols=10, $rows=10, $color="green"){
static $count=0;
$count++;
echo '<table border="1">';
for($tr=1; $tr<=$rows; $tr++){
echo "<tr>";
for($td=1; $td<=$cols; $td++){
if($td==1 or $tr==1){
echo "<th style='background-color:$color'>", $tr * $td, "</th>";
} else {
echo "<td>", $tr * $td, "</td>";
}
}
echo "</tr>";
}
echo '</table>';
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
getTable();
echo "Таблица была отрисована " . $count . " раз";
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
  <?php
//Инициализация массива
	$leftMenu = array(
		array('link'=>'Домой', 'href'=>'index.php'),
		array('link'=>'О нас', 'href'=>'about.php'),
		array('link'=>'Контакты', 'href'=>'contact.php'),
		array('link'=>'Таблица умножения', 'href'=>'table.php'),
		array('link'=>'Калькулятор', 'href'=>'calc.php'),
		);
//Функция отрисовки меню
function drawMenu($menu, $vertical = TRUE) {
	$style = '';
	//Горизонталь или вертикаль
	if(!$vertical){
        $style = " style=display:inline";
	}
	echo "<ul$style>";
	foreach($menu as $item){
	echo "<li>";
	echo "<a href='{$item[href]}'>{$item[link]}</a>";
	echo "</li>";	
	}		
	echo "</ul>";
   }
   ?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"> 
  <?php
    // Объявление константы
    define('COPYRIGT','Супер мега мастер');
    // Установка локали и выбор значений даты
       setlocale (LC_ALL, "russian");
      $day = strftime('%d');
      $mon = strftime('%m');
      $year = strftime('%Y');
      $hour = strftime('%H');// Переводит строку в целое число
      $welcome ='';// Инициализирует переменную для приветствия
      if($hour >=23 && $hour =4){
      $welcome ='Доброй ночи';
     }
      elseif($hours >4&&$hours<=11){
      $welcome ='Доброе утро';
    }
      elseif($hours >=11&&$hours <=18){
      $welcome ='Добрый день';
    }
      elseif($hours <=18&&$hours >=23){
      $welcome ='Добрый вечер';
    }
    else{
        $welcome = 'Доброй день';
    }
   ?> 
	<head>
		<title>Сайт нашей школы</title>
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
			<h1><?php echo$welcome?> гость !</h1>
			<!-- Заголовок -->
			<!-- Область основного контента -->
			<blockquote>
			<?php echo "Сегодня $day число,$mon месяц,$year год.";?>
			<h3>Зачем мы ходим в школу?</h3>
			</blockquote>
			<p>
			У нас каждую минуту что-то происходит и кипит жизнь. Проходят уроки и шумят перемены, кто-то отвечает у доски, кто-то отчаянно зубрит перед контрольной пройденный материал, кому-то ставят «пятерку» за сочинение, кого-то ругают за непрочитанную книгу, на школьной спортивной площадке ребята играют в футбол, а девочки – в волейбол, некоторые готовятся к соревнованиям, другие участвуют в репетициях праздников…
			</p>
			<!-- Область основного контента -->
			</div>
		<div id="nav">
			<!-- Навигация -->
			<h2>Навигация по сайту</h2>
			<!-- Меню -->
		    <?php
			//Рисуем меню
			drawMenu($leftMenu);
		    ?>
			<!-- Меню -->
			<!-- Навигация -->
		</div>
		<div id="footer">
			<!-- Нижняя часть страницы -->
			<?=strftime('%Y')?>
			&copy; Copyright, 2017 - 2018
			<? echo COPYRIGT?>
			<!-- Нижняя часть страницы -->
		</div>
	</body>
</html>
