# -css-grid


.box{
display: grid;
grid-template-columns:300px 300px 300px;  /* 3 колонки по 300px */
grid-template-rows: 200px 200px;/*  2 ряда по 200пкс  остальные дефолтные*/
grid-auto-rows: 100px; /* для дефолтных значений */
grid-auto-columns: 100px; /* для дефолтных значений */
grid-column-gap: 20px; /* расстояние между элементами */
grid-row-gap: 20px; /* расстояние между элементами */
grid-gap: 20px; /* расстояние между элементами (общие) */
grid-template: repeat(3,200px) / repeat(4, 1fr);


						/* АДАПТИВНЫЕ ЕДИНИЦЫ ИЗМЕРЕНИЯ */
grid-template-columns:1fr 2fr; /*  фракция занимающая одну часть экрана из 3х, и 2е из 3х
								для фиксированного блока пишем пиксели */

						/* ПОВТОРЕНИЕ СВОЙСТВ */
grid-template-columns:repeat(4,1fr); - /* 4 колонки по 1фракции */
grid-template-columns:repeat(2,1fr 2fr); /*  череда колонок 1фракция / 2 фракции/ 1 фракция ... */
grid-template-columns: 100px repeat(2,1fr 2fr);  /* 1я коолнка 100, дальше повтор */


						/* ОТЗЫВЧИВЫЙ ВЕРСТКА (responsive) */
grid-template-columns:minmax(100px, 200px) 1fr; /* 1я колонка 200px, при прижатии уменьшатся до 100px. 2я и 3я колонка резиновые */
grid-auto-rows: minmax(100px, auto); /* минимальная 100, максимальная автоматическая. */
grid-auto-flow: column/row; /* изменит направление ячеек, нужно GTR и GTC  */


grid-template-columns:repeat(auto-fill,200px/minmax()); - /* изменяется количество колонок при уменьшении экрана */
grid-template-columns:repeat(auto-fit,200px/minmax());/*  при auto-fit  не перескакивают на др строчку. */

}

						/* Изменение позиции блоков */
.grid div:nth-child(1){
	grid-column-start: 2;  - /* item 1 съедит на позицию 2 */
	grid-column-end: 5; /* на всю ширину болков растягивается элемент (5ти блоков) */
	grid-column: 1 / 5; /* сокращенная запись */
	align-self: start, center, stretch, end; 
	justify-self: start, center, stretch, end; 
}
.grid div:nth-child(2){
	grid-column: 1;
	grid-row: 2;   /* в какой строчке */
}
.grid div:nth-child(3){
	grid-column: 2/4;
	grid-row: 2;
}

						/* Выравнивание всех элементов */
.grid{
	justify-items: start, center, stretch, end; /* горизонтальное  */
	align-items: start, center, stretch, end; /* вертикальное */
}




.grid{
	display: grid;
	grid-template-areas: 
		"header"
		"article"
		"aside"
		"footer" ;
}										/* 	макет блоков для моб версий		 */					
header{
	grid-area: header;
}
article{
	grid-area: article;
}
aside{
	grid-area: aside;
}
footer{
	grid-area: footer;
}
@media (min-width: 	640px){
	.grid{
		grid-template-columns: 2fr 4fr;
		grid-template-areas: 
		"header header"
		"aside article"
		"footer footer" ; /*  можно поставить точку (символизирует пустоту) */
	}
}

/* Так же можно работать с вложенными DIV */
