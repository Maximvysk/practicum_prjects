# Мобильные игры - корректировка модели монетизации
## Материалы
* [Презентация](https://drive.google.com/file/d/1E-26cfrNocJzIRJnvfuoSJ82NZ3C8MZk/view?usp=sharing)
* [Дашборд](https://public.tableau.com/views/Dash_Final_project/sheet4?:language=en-US&:display_count=n&:origin=viz_share_link)
## Описание проекта
Основные проблемы с которыми сталкиваются разработчики игр:

- Пользователь разозлится и уйдёт, если начать показывать ему рекламу раньше, чем игра его затянет.
- Но  чем позже создатели игры включат рекламу, тем меньше они заработают.

Наша задача помочь бизнесу выбрать оптимальное время для начала показа рекламы

#### Стек инструментов
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
from scipy import stats as st
import math

# Оглавление
1. [Открытие данных и изучение общей информации](#start)
2. [Подготовка данных](#preprocessing)
3. [Исследовательский анализ данных](#exploratory_analysis)
4. [Маркетинговый анализ данных](#marketing_analysis)
5. [Статистический анализ данных](#statistic_analysis)
6. [Формирование модели монетизации](#monetisation_model)
7. [Общие выводы и презентация](#general_conclusion)

game_actions  
- `event_datetime` — время события;
- `event` — одно из трёх событий:
    1. `building` — объект построен,
    2. `finished_stage_1` — первый уровень завершён,
    3. `project` — проект завершён;
- `building_type` — один из трёх типов здания:
    1. `assembly_shop` — сборочный цех,
    2. `spaceport` — космопорт,
    3. `research_center` — исследовательский центр;
- `user_id` — идентификатор пользователя;
- `project_type` — тип реализованного проекта;

ad_costs
- `day` - день, в который был совершен клик по объявлению
- `source` - источник трафика
- `cost` - стоимость кликов

user_source
- `user_id` - идентификатор пользователя
- `source` - источников, с которого пришёл пользователь, установивший приложение