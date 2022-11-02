Требования к проекту

Введение

1.1 Назначение

В этом документе описаны функциональные и нефункциональные требования к приложению "Uno online" - браузерной версии игры "Uno". Этот документ предназначен для команды, которая будет реализовывать и проверять корректность работы приложения. 

1.2 Бизнес требования

1.2.1 Исходные данные

Uno - карточная настольная игра, целью которой является избавление от всех карт. На сегодняшний день в мире более 150 000 000 людей успели купить Uno. За более чем 50 лет существования свою популярность игра обрела относительно недавно.

1.2.2 Возможности бизнеса

Многие, заинтересованные в настольных играх, молодые люди хотели бы иметь доступ к любимой игре не имея её физически, а также быстро находить компанию для игры.

1.2.3 Границы проекта

Приложение "Uno online" не разделяет зарегистрированных и анонимных пользователей по основным функциональным возможностям, а именно: создание игровой комнаты и присоединение к ней, пользование игровым чатом, доступ к таблице лидеров. Помимо основного функционала для зарегистрированных пользователей будет доступен магазин для изменения частей пользовательского интерфейса: карт для игры, иконки профиля. 

1.3 Аналоги

Одним из многочисленных аналогов является площадка boardgamearena, где игроки со всего мира могут сыграть в более чем 500 настольных игр в браузере. Однако для доступа к играм и созданию игровых комнат пользователю необходимо зарегестрироваться, что, безусловно, является отталкивающим фактором для выбора платформы новыми игроками. Среди плюсов можно выделить:
  - наличие чата в игровой комнате
  - возможность приостановить игру
  - возможность просмотра истории ходов
  - сезонные таблицы лучших игроков
  - система наград, не влияющая на "баланс" игрового процесса
  
2. Требования к пользовательскому интерфейсу

2.1 Интерфейс пользователя

Главное окно с профилем игрока.

/src/resources/static/main_menu.png

Окно регистрации.

/src/resources/static/main_menu.png

Окно создания комнаты.

/src/resources/static/create_room.png

Окно поиска комнаты.

/src/resources/static/find_room.png

Окно таблицы лидеров.

/src/resources/static/leaderboard.png

2.2 Классы пользователей

Анонимные пользователи - пользователи, не создавшие аккаунт, они имеют доступ к созданию/поиску комнат, чату, просмотру таблицы лидеров. Такие игроки при входе на сайт вводят лишь имя пользователя. Они не получают очков за победы, не могут попасть в таблицу лидеров, у них нет статистики аккаунта.

Зарегистрированные пользователи - пользователи, создавшие учетную запись. Таким пользователям помимо функций создания/поиска комнат, доступа чату, просмотра таблицы лидеров доступны: статистика профиля, магазин покупки стилей для карт и для иконки профиля. Также они могут сами попасть в топ игроков, получив награду. Внутриигровой валютой в магазине являются очки, начисляющиеся после выигранных игр.

3. Системные требования

3.1 Функциональные требования

3.1.1 Вход пользователя в приложение

| Функция | Требования | 
|:---|:---|
| Вход в приложение без создания собственного профиля | Приложение должно предоставить пользователю возможность войти в приложение без учетной записи |
| Регистрация нового пользователя | Приложение должно запросить у пользователя ввести уникальное игровое имя для создания учётной записи. Пользователь должен либо ввести имя, либо отменить действие |
| Вход зарегистрированного пользователя в приложение | Приложение должно использовать cookie для аутентификации пользователя |

3.1.2 Создание игровой комнаты

| Функция | Требования | 
|:---|:---|
| Создание игровых комнат | В приложении должно быть реализовано соответствующее окно со следующими полями для ввода/выбора пользователем настроек комнаты: название, доступ (общедоступный/приватный), количество игроков,  выбор правил игры | 
| Создание приватных комнат | Приложение должно предоставить пользователю возможность ввести пароль для доступа к комнате |
| PVE режим игры | В приложении должна быть функция игры против ботов. Приложение должно предоставить 3 уровня сложности ботов на выбор пользователя |

3.1.3 Поиск игровой комнаты 

| Функция | Требования | 
|:---|:---|
| Список игровых комнат | Приложение должно предоставить пользователю список комнат со всеми настройками, указанными при её создании. Если пользователь входит в приватную комнату должно быть реализовано окно ввода пароля |
| Загрузка игровых комнат | Приложение должно использовать pagination для отображения списка комнат. При этом должна быть реализована и выбрана по умолчанию сортировка комнат по заполненности игроками |

3.1.4 Просмотр игровой статистики

| Функция | Требования | 
|:---|:---|
| Хранение данных в статистике | Приложение должно хранить и отображать статистику в профилях зарегестированных пользователей. В окне статистики должны быть: количество сыгранных матчей и побед, количество очков и место в таблице лидеров. При этом количество очков является информацией, которая видна только самому игроку. Место в таблице лидеров обновляется каждые 3 месяца на основе соотношения матчей и побед |

3.1.5 Наличие чата в главном окне приложения

| Функция | Требования | 
|:---|:---|
| Отправка сообщений | Длина сообщения не более 256 символов. В приложении также должна быть возможность отправки эмодзи |
| Добавление ссылки на игровую комнату | Пользователь с созданной комнатой может ввести ссылку на вход в его комнату. При нажатии на такую ссылку другие пользователи будут перенаправлены в игровую комнату данного пользователя |

3.2 Нефункциональные требования
