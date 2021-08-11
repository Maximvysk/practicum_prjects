# Рынок заведений общественного питания Москвы
## Описание проекта
Объект исследования - рынок общественного питания Москвы. Задача - выяснить сможет ли занять свою нишу наше заведение и какую локацию лучше всего рассматривать

#### Стек инструментов
import pandas as pd
import numpy as np
import plotly.express as px
import datetime as dt
import plotly.graph_objects as go
import requests
from bs4 import BeautifulSoup
import re
from io import BytesIO

# Оглавление
1. [Загрузка данных и подготовка их к анализу](#start)
    * [Откроем файл с данными и изучим общую информацию](#opening)
    * [Подготовка данных](#preprocessing)
2. [Анализ данных](#exploratory_analysis)
3. [Презентация](#presentation)
4. [Общий вывод](#general_conclusion)

Таблица rest_data:  
* id — идентификатор объекта
* object_name — название объекта общественного питания
* chain — сетевой ресторан
* object_type — тип объекта общественного питания
* address — адрес
* number — количество посадочных мест