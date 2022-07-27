# Что такое LaTeX?

LATEX используется во всем мире для научных документов, книг, а также во многих других формах публикации. Онпозволяет создавать красиво набранные документы, быстро выполнять более сложные части набора текста, такие как ввод математических данных, создание оглавлений, ссылок и библиографий, а также согласованное расположение всех разделов. Благодаря огромному количеству доступных пакетов возможности LATEX безграничны. Эти пакеты позволяют пользователям делать при помощи LATEX много нужных и полезных вещей, например добавлять сноски, рисовать схемы, создавать таблицы и т.д.

# Создание первого документа, используя Overleaf

Сначала нужно определить класс вашего документа с помощью команды **\documentclass**, обозначить начало и конец документа при помощи команд **\begin{document}** и **\end{document}**, между данными двумя строчками кода будет заключено тело документа. Первая строчка кода будет обозначать класс, например *article*, *book*, *report*, самый частовстречаемый это *article*, и чтобы указать данный класс достаточно прописать первой строчкой **\documentclass{article}**.

### Преамбула

Код, который написан до команды **\begin{document}** называется преамбулой. В преамбуле следует определить тип документа, который вы пишете, язык, на котором вы пишете, пакеты, которые вы хотели бы использовать, и некоторые другие элементов. Стандартная преамбула может выглядеть следующим образом: 

**\documentclass[12pt, letterpaper]{article}**

**\usepackage[utf8]{inputenc}**

Как уже было сказано ранее, первая строка определяет тип документа, а в квадратные скобки могут быть переданы некоторые дополнительные параметры, разделенные запятой, в данном случае **12pt** задает размер шрифта, а **letterpaper** размер листа. Вторая строка отвечает за кодировку, используемую в документе. Если вам не нужна какая то специфическая, то просто добавьте эту строку в ваш документ.

К примеру можно установить следующий пакет: **\usepackage{babel} **, который отвечает за поддержку нескольких языков в вашем документе.

### Заголовок, автор и дата

Для того чтобы указать заголовок, автора и дату, необходимо пропсасть следующие 3 строки в ПРЕАМБУЛЕ:

**\title{Ваш заголовок}**

**\author{Ваш автор}**

**\date{Ваша дата}**.

Чтобы отобразить это непосредственно в самом документе, достаточно после строки **\begin{document}** прописать **\maketitle**.

### Комментарии

В LaTeX вы можете добавлять комментарии с помощью знака процента **%**, вся строка которая после него следует будет закомментирована, то есть не будет отображаться в документе после компиляции.

### Жирный шрифт, курсив и подчеркивание

Выделение жирным шрифтом: **\textbf{ваш текст}**;

Выделение курсивом: **\textit{ваш текст}**;

Подчеркивание текста: **\underline{ваш текст}**;

### Добавление картинок

Для начала, вам нужно загрузить картинку в ваш проект, пусть она называется image.png, тогда чтобы просто встаить ее в документе в какое- то место, достаточно в нем прописать **\includegraphics{universe}**, при этом в преамбуле потребуется также подключить следующие пакеты:

**\usepackage{graphicx}**

**\graphicspath{ {images/} }**

Чтобы группировать картинки, делать к ним подписи, и получить доступ к дополнительным опциям, потребуется обрамлять вашу картинку **\begin{figure}** и **\end{figure}**, подключив следующие пакеты:

```latex
//latex code
\usepackage{caption}  
\usepackage{graphicx}  
\usepackage{caption}
\usepackage{subfigure}
```

### Подписи, лэйблы и ссылки

**\caption{picture}**: Эта команда задает заголовок для рисунка. Если вы создадите список рисунков, там будет использоваться эта подпись. Вы можете разместить его над или под рисунком.

**\label{fig:pic1}**: Если вам нужно сослаться на изображение в вашем документе, установите метку с помощью этой команды. Метка пронумерует изображение и в сочетании со следующей командой позволит вам ссылаться на него.

(Предыдущие две команды следует прописать между **\begin{figure}** и **\end{figure}**).

**\ref{fig:pic1}**: Этот код будет заменен номером, соответствующим указанному рисунку.

### Списки
Нужны, когда вам потребуется что то перечислить.

1) Непронумерованные списки
Понятно на примере кода:
```latex
//latex code
\begin{itemize}
  \item 1
  \item 2
\end{itemize}
```

2) Пронумерованные списки
```latex
//latex code
\begin{enumerate}
  \item 1
  \item 2
\end{enumerate}
```

3) Вложенные списки
Также списки можно вкладывать друг в друга:
```latex
//latex code
\begin{enumerate}
  \item \begin{itemize}
            \item 1
             \item 2
         \end{itemize}
  \item 2
\end{enumerate}
```

### Разделение на главы, секции, подсекции и тд.

Формат book в Latex поддерживает разделение текста на главы, форматы article и papper -- нет, но поддерживают разделение на любые части, стоящие ниже в иерархии. Чтобы их указать, достаточно прописать одну из следующих команд(далее расположены в порядке иерархии от наиболее важной к менее):

```latex
//latex code
\part{part}
\chapter{chapter}
\section{section}
\subsection{subsection}
\subsubsection{subsubsection}
\paragraph{paragraph}
\subparagraph{subparagraph}
```


### Создание таблиц

Приведем самый простой пример таблицы, которую можно создать при помощи Latex:

```latex
//latex code
\begin{center}
\begin{tabular}{ c c c }
 1 & 2 & 3 \\ 
 4 & 5 & 6 \\  
 7 & 8 & 9    
\end{tabular}
\end{center}
```

В таблице, соответствующей данному коду, не будет никаких линий, ни горизонтальных, ни вертикальных, чтобы добавить разметку, необходимо 


