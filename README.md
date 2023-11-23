# lab12
#1esep
import pandas as pd
# Создаем датасет вручную
data = {
    'Name': ['Jeff Bezos', 'Elon Musk', 'Bernard Arnault & family', 'Bill Gates', 'Mark Zuckerberg', 'Warren Buffett'],
    'Net_Worth_Billion': [177, 151, 150, 124, 97, 96],
    'Age': [57, 50, 73, 66, 37, 91],
    'Industry': ['Technology', 'Technology', 'Fashion & Retail', 'Technology', 'Technology', 'Finance & Investments'],
    'Country': ['United States', 'United States', 'France', 'United States', 'United States', 'United States'],
    'Source_of_Wealth': ['Amazon', 'Tesla, SpaceX', 'LVMH', 'Microsoft', 'Facebook', 'Berkshire Hathaway']
}
# Создаем датафрейм
full_health_data = pd.DataFrame(data)
# Устанавливаем опции для отображения всех столбцов и строк
pd.set_option('display.max_columns', None)
pd.set_option('display.max_rows', None)
# Выводим статистическое описание датасета
print(full_health_data.describe())


#2esep
import numpy as np
import pandas as pd
# Создаем датасет о здоровье вручную
data = {
    'Duration': [60, 60, 60, 45, 45, 60, 60, 45, 30, 60, 60, 60, 60, 60, 60, 60, 60, 45, 60, 45],
    'Average_Pulse': [110, 117, 103, 109, 117, 102, 110, 104, 109, 98, 103, 100, 106, 104, 98, 98, 100, 90, 103, 97],
    'Max_Pulse': [130, 145, 135, 175, 148, 127, 136, 134, 133, 124, 147, 120, 128, 132, 123, 120, 120, 112, 123, 125],
    'Calorie_Burnage': [409, 479, 340, 282, 406, 300, 374, 253, 195, 269, 329, 250, 345, 379, 275, 215, 300, 180, 323, 243],
    'Hours_Work': [0, 0, 8, 8, 0, 0, 0, 0, 8, 7.5, 8, 0, 8.5, 8.5, 9, 6.5, 9, 8, 8, 8],
    'Hours_Sleep': [8, 8, 7.5, 8, 6.5, 7.5, 7.5, 9, 8, 8, 7, 5, 7.5, 7.5, 7, 6, 8, 8, 8, 7]
}
# Создаем датафрейм
full_health_data = pd.DataFrame(data)
# Вычисляем 10-й перцентиль для столбца "Max_Pulse"
max_pulse_10th_percentile = np.percentile(full_health_data["Max_Pulse"], 10)
# Выводим результат
print(f"10-й перцентиль Max Pulse: {max_pulse_10th_percentile}")


#3esep
import pandas as pd
import numpy as np
# Создаем датасет о миллиардерах вручную
data = {
    'Name': ['Jeff Bezos', 'Elon Musk', 'Bernard Arnault & family', 'Bill Gates', 'Mark Zuckerberg', 'Warren Buffett'],
    'Net_Worth_Billion': [177, 151, 150, 124, 97, 96],
    'Age': [57, 50, 73, 66, 37, 91],
    'Industry': ['Technology', 'Technology', 'Fashion & Retail', 'Technology', 'Technology', 'Finance & Investments'],
    'Country': ['United States', 'United States', 'France', 'United States', 'United States', 'United States'],
    'Source_of_Wealth': ['Amazon', 'Tesla, SpaceX', 'LVMH', 'Microsoft', 'Facebook', 'Berkshire Hathaway']
}
# Создаем датафрейм
billionaires_data = pd.DataFrame(data)
# Вычисляем стандартное отклонение для каждого столбца
std_deviation_billionaires = np.std(billionaires_data[['Net_Worth_Billion', 'Age']])
# Выводим результат
print("Стандартное отклонение для каждого столбца в датасете о миллиардерах:")
print(std_deviation_billionaires)


#4esep
import pandas as pd
import numpy as np
# Создаем датасет о росте вручную
data = {
    'Name': ['Alice', 'Bob', 'Charlie', 'David', 'Eva'],
    'Height': [165, 180, 175, 160, 170]
}
# Создаем датафрейм
height_data = pd.DataFrame(data)
# Вычисляем дисперсию для столбца "Height"
variance_height = np.var(height_data['Height'])
# Выводим результат
print("Дисперсия роста:")
print(variance_height)


#5esep
import pandas as pd
import matplotlib.pyplot as plt
# Создаем датасет о миллиардерах вручную
data = {
    'Name': ['Jeff Bezos', 'Elon Musk', 'Bernard Arnault', 'Bill Gates', 'Mark Zuckerberg', 'Warren Buffett'],
    'Net_Worth_Billion': [177, 151, 150, 124, 97, 96],
    'Age': [57, 50, 73, 66, 37, 91],
    'Country': ['United States', 'United States', 'France', 'United States', 'United States', 'United States'],
    'Industry': ['Technology', 'Technology', 'Fashion & Retail', 'Technology', 'Technology', 'Finance & Investments']
}
# Создаем датафрейм
billionaires_data = pd.DataFrame(data)
# Вычисляем коэффициент корреляции Пирсона
correlation_coefficient = billionaires_data['Age'].corr(billionaires_data['Net_Worth_Billion'])
# Создаем точечную диаграмму
plt.scatter(billionaires_data['Age'], billionaires_data['Net_Worth_Billion'])
plt.title('Age vs Net Worth\nCorrelation Coefficient: {:.2f}'.format(correlation_coefficient))
plt.xlabel('Age')
plt.ylabel('Net Worth (Billion $)')
plt.show()


#6esep
import pandas as p
# Создание вручную заполненного датасета
data = {'Feature1': [1, 2, 3, 4, 5],
        'Feature2': [5, 4, 3, 2, 1],
        'Feature3': [2, 3, 1, 4, 5],
        'Feature4': [3, 1, 4, 2, 5]}
df = pd.DataFrame(data)
# Рассчет корреляционной матрицы
correlation_matrix = df.corr()
# Вывод корреляционной матрицы
print("Correlation Matrix:")
print(correlation_matrix)



#7esep
import pandas as pd
# Создаем вручную заполненный датасет о миллиардерах
data = {
    'Age': [35, 50, 42, 60, 45],
    'Net_Worth_Billion': [2.5, 5.3, 1.8, 8.7, 4.2],
    'Years_of_Education': [16, 18, 14, 20, 17],
    'Number_of_Companies': [3, 1, 2, 5, 4]
}
df = pd.DataFrame(data)
# Рассчет корреляционной матрицы
correlation_matrix = df.corr()
# Вывод корреляционной матрицы
print("Correlation Matrix:")
print(correlation_matrix)
