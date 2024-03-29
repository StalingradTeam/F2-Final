# Краткая шпаргалка по tmux (менеджеру терминалов)

Настройка Linux

tmux — это менеджер терминалов, к которому удобно подключаться и отключаться, не теряя при этом процессы и историю. Как screen, только лучше (в первую очередь потому, что использует модель клиент—сервер).

image

Вашему вниманию предлагается минималистическая шпаргалка, позволяющая быстро начать использовать tmux, а уж тонкую настройку, продвинутые команды и бесконечные хот-кеи желающие найдут, набрав man tmux.



Очень хороший способ запустить tmux:
tmux attach || tmux new — делая так, вы сперва пытаетесь подключиться к уже существующему серверу tmux, если он существует; если такого ещё нет — создаёте новый.

После этого вы попадаете в полноценную консоль.
Ctrl+b d — отключиться. (Точно так же вы отключитесь, если прервётся соединение. Как подключиться обратно и продолжить работу — см. выше.)

В одной сессии может быть сколько угодно окошек:

Ctrl+b c — создать окошко;

Ctrl+b 0...9 — перейти в такое-то окошко;

Ctrl+b p — перейти в предыдущее окошко;

Ctrl+b n — перейти в следующее окошко;

Ctrl+b l — перейти в предыдущее активное окошко (из которого вы переключились в текущее);

Ctrl+b & — закрыть окошко (а можно просто набрать exit в терминале).

В одном окошке может быть много панелей:

Ctrl+b % — разделить текущую панель на две, по вертикали;

Ctrl+b " — разделить текущую панель на две, по горизонтали (это кавычка, которая около Enter, а не Shift+2);

Ctrl+b ><^v — переходить между панелями;

Ctrl+b x — закрыть панель (а можно просто набрать exit в терминале).

Недостаток — непривычным становится скроллинг:

Ctrl+b PgUp — вход в «режим копирования», после чего:

PgUp, PgDown — скроллинг;

q — выход из «режима копирования».