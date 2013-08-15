task-force-arma-3-radio
=======================

Arma 3 Team Speak Radio Plugin

Инструкция по установке:

* Скачайте [архив с рацией 0.5.0 alpha](https://github.com/michail-nikolaev/task-force-arma-3-radio/raw/master/releases/0.5.0%20alpha.zip)
* Убедитесь, что в Team Speak клавиша Caps Lock не используется для разговора
* Убедись, что вы запускаете игру только один раз (только одно окно игры)
* Отключите в ARMA 3 разговор по внутренней рации по нажатию Caps Lock (чтобы не двоиться)
* Скопируйте содержимое папки Arma 3 в `....\SteamApps\common\Arma 3` (папку с игрой)
* Скопируйте содержимое `TeamSpeak 3 Client\x32` в папку с TeamSpeak если он 32-ух битный, или `TeamSpeak 3 Client\x64`, если 64-ёх
* Чтобы узнать, какой у вас TeamSpeak поищите файл `ts3client_win64.exe` или `ts3client_win32.exe` в папке с Team Speak
* Запустите Team Speak, зайдите на любой сервер, кликните правой кнопкой на вашем канале и выберите `Setup 3D Sound`, установите галочку `Enable 3D Sound` слева снизу
* Откройте список плагинов в Team Speak, включите `Task Force Arma 3 Radio`, отключите `ACRE` и `radio ts ARMA3.ru version` (если они есть), чтобы избежать конфликтов
* Можно на всякий случай перезапустить Team Speak :)
* Запустите игру с аддонами `CBA_A3` и `@task_force_radio` (Community Base Addons: A3 Beta и Task Force Arrowhead Radio), это можно сделать командой `arma3.exe -mod:@CBA_A3;@task_force_radio`
* Убедитесь, что ник в игре и Team Speak совпадает (если вы используете squal url, то добавляемый им в конец ника тэг не стоит ичитывать)
* Убедитесь, что громкость звуков в Team Speak не отключена (Options -> Payback -> Sound Pack Volume установите на максимум +0db)
* Рекомендуется отключить звуки-оповещения TeamSpeak: Options -> Notifications -> Sound Pack: "Sounds Deactivated" (применится только после перезапуска Team Speak)
* Зайдите в тот же канал, где и другие игроки с данной рацией

Управление:
* Используйте кнопку разговора в Team Speak, чтобы говорить прямой речью
* Используйте `CTRL` + `P`, чтобы открыть интерфейс коротковолновой рации (у вас в инвентаре должна быть рация в слоте). Для того, чтобы ввести частоту нажмите `CLR`, введите значение и нажмите `ENT`
* Используйте `Caps Lock`, чтобы говорить по рации
* Используйте `ALT` + `P`, чтобы открыть интерфейс рации дальней связи (у вас в инвентаре должна быть рация в слоте). Для того, чтобы ввести частоту нажмите `MENU CLR`, введите значение и нажмите `FREQ`
* Используйте `CTRL` + Caps Lock`, чтобы говорить по рации дальней связи
* Управление можно настроить посредством редактирования `userconfig\task_force_radio\radio_keys.hpp`

Частоты:
* Рация [AN/PRC-152](http://ru.wikipedia.org/wiki/AN/PRC-152) (коротковолновая) может работать на частотах от 30 до 512 MHz.
* Рация [RT-1523G (ASIP)](http://en.wikipedia.org/wiki/SINCGARS#Models) работает на частотах от 30 до 87 MHz.
* Обе рации поддерживают SINCGARS протокол, поэтому могут связываться друг с другом. В случае если передача осуществляется с [AN/PRC-152](http://ru.wikipedia.org/wiki/AN/PRC-152), звук будет высокочастотным. В случае передачи с [RT-1523G (ASIP)](http://en.wikipedia.org/wiki/SINCGARS#Models) - низкочастотным. 


**Пояснения о режимах:**
* Плагин поддерживает два режима работы - "серьезный" и "несерьезный". 
* "Несерьезный" режим используется по умолчанию. Он предназначен главным образом для кооперативных игр. Его особенностью является то, что игроки с плагином и в игре слышат мертвых, не играющих, играющих на другом сервере и играющих без плагина игроков минуя рацию (просто как через TeamSpeak). Это делает не удобным игры против людей, но позволяет вашему другу без проблем узнать, где вы играете, какая у вас частота и т.д. Разумется, те кто играет на одном сервере со включенными аддонами и плагинами будут слышать друг друга по "законам" рации (с учетом расстояния и частот).
* "Серьезный" режим предназначен для проведения игр, где игроки играют против других игроков. Для его активации необходимо создать канал с названием `TaskForceRadio` и паролем `123`. Игроки должны включить плагин рации, зайти на сервер и, разойдясь по каналам сторон, брифинговать. При старте миссии через несколько секунд игроки будут переброшены в канал `TaskForceRadio`. В данном случае игроки будут слышать только живых игроков со включенным плагином играющих на этом же сервере. Мертвые игроки, в свою очередь, могут общаться друг с другом. Если мертвый игрок респавниться - он снова будет слышать только живых. После того, как игра заканчивается, игроки перебрасываются в канал, в котором они брифинфовали до игры.

На всякий случай:
* Если из-за ошибки или еще чего-то вы перестали слышать других игроков даже вне игры, откройте `Setup 3D Sound` и скликните `Center All`

Администраторам TeamSpeak серверов:
* Уменьшите уровень защиты от флуда - правый клик по серверу -> Edit Virtual Server -> More -> Anti Flood, поставьте значения 30, 300, 3000 (сверху вниз)

Разработчикам:
* Если уж данная разработка будет как-либо популярна, то хотелось бы избежать кучи несовместимых форков. По этой причине в случае желания внесения изменений связывайтесь со мной - велика вероятность, что ваши разработки будут вмержены в главную ветку. Ждем ваших Pull Requests :)

Спасибки:
* Отряду [Task Force Arrowhead](http://forum.task-force.ru/) за тестирование, поддержку, терпение и всяческую помощь, лично [MTF](http://forum.task-force.ru/index.php?action=profile;u=7) за помощь в графической части
* [Блендеру](http://arma3.ru/forums/index.php/user/41-blender/) за шрифт