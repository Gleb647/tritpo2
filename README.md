Требования к проекту

<h5>1. Введение<h5>

1.1 Назначение

В этом документе описаны функциональные и нефункциональные требования к приложению "Uno online" - браузерной версии игры "Uno". Этот документ предназначен для команды, которая будет реализовывать и проверять корректность работы приложения. 

1.2 Бизнес требования

1.2.1 Исходные данные

Uno - карточная настольная игра, целью которой является избавление от всех карт. На сегодняшний день в мире более 150 000 000 людей успели купить Uno. За более чем 50 лет существования свою популярность игра обрела относительно недавно, в связи с чем появился спрос на её разработку для онлайн-платформ с настольными играми.

1.2.2 Возможности бизнеса

Многие, заинтересованные в настольных играх, молодые люди хотели бы иметь онлайн-доступ к любимой игре, а также быстро находить компанию для игры.

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

<img src="/src/resources/static/main_menu.png" width="1100">

Окно регистрации.

<img src="/src/resources/static/register.png" width="1100">

Окно создания комнаты.

<img src="/src/resources/static/create_room.png" width="1100">

Окно поиска комнаты.

<img src="/src/resources/static/find_room.png" width="1100">

Окно таблицы лидеров.

<img src="/src/resources/static/leaderboard.png" width="1100">

2.2 Классы пользователей

Анонимные пользователи - пользователи, не создавшие аккаунт, они имеют доступ к созданию/поиску комнат, чату, просмотру таблицы лидеров. Такие игроки не вводят никаких данных при входе на сайт. Они не получают очков за победы, не могут попасть в таблицу лидеров, у них нет статистики аккаунта.

Зарегистрированные пользователи - пользователи, создавшие учетную запись. Таким пользователям помимо функций создания/поиска комнат, доступа чату, просмотра таблицы лидеров доступны: статистика профиля, магазин покупки стилей для карт и для иконки профиля. Также они могут сами попасть в топ игроков, получив награду. Внутриигровой валютой в магазине являются очки, начисляющиеся после выигранных игр.

3. Системные требования

3.1 Функциональные требования

3.1.1 Вход пользователя в приложение

| Функция | Требования | 
|:---|:---|
| Вход в приложение без создания собственного профиля | Приложение должно предоставить пользователю возможность войти в приложение без учетной записи |
| Регистрация нового пользователя | Приложение должно запросить у пользователя ввести уникальное игровое имя и пароль для создания учётной записи. Пользователь должен либо ввести имя и пароль, либо отменить действие |
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
| Хранение данных в статистике | Приложение должно хранить и отображать статистику в профилях зарегистированных пользователей. В окне статистики должны быть: количество сыгранных матчей и побед, количество очков и место в таблице лидеров. При этом количество очков является информацией, которая видна только самому игроку. Место в таблице лидеров обновляется каждые 3 месяца на основе соотношения матчей и побед |

3.1.5 Наличие чата в главном окне приложения

| Функция | Требования | 
|:---|:---|
| Отправка сообщений | Длина сообщения не более 256 символов. В приложении также должна быть возможность отправки эмодзи |
| Добавление ссылки на игровую комнату | Пользователь с созданной комнатой может ввести ссылку на вход в его комнату. При нажатии на такую ссылку другие пользователи будут перенаправлены в игровую комнату данного пользователя |

3.2 Нефункциональные требования

3.2.1 Атрибуты качества

3.2.1.1 Требования к удобству использования

1. Доступ к основным функциям приложения не более чем за две операции;
2. Все функциональные элементы пользовательского интерфейса имеют названия, описывающие действие, которое произойдет при выборе элемента;

3.2.1.2 Требования к безопасности

В приложении должно быть реализовано хэширование паролей учетных записей пользователей.

3.2.2 Внешние интерфейсы

Окна приложения удобны для использования пользователями с плохим зрением:
  * размер шрифта не менее 14пт;
  * функциональные элементы контрастны фону окна.

3.2.3 Ограничения

1. Приложение реализовано в laravel 9.28.0;
2. Профиль пользователя хранится в файле с расширением XML, название файла совпадает с именем (псевдонимом).
