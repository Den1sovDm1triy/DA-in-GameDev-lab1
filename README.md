# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Мокроносов Александр Сергеевич
- РИ210950
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Структура отчета

- Данные о работе: название работы, фио, группа, выполненные задания.
- Цель работы.
- Задание 1.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 2.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Задание 3.
- Код реализации выполнения задания. Визуализация результатов выполнения (если применимо).
- Выводы.
- ✨Magic ✨

## Цель работы
Ознакомиться с работой перцептрона.

## Задание 1
### В проекте Unity реализовать перцептрон, который умеет производить вычисления.

Ход работы:

1. Создаём пустой проект в unity.

2. Добавляем пустой объект Empty Game Object с именем Perceptron.

![image](https://user-images.githubusercontent.com/113508468/205235934-37c1eab4-2809-491d-ab13-5e1912303422.png)

3. Подключаем Perceptron.cs к пустому Game Object с именем Perceptron.

![image](https://user-images.githubusercontent.com/113508468/205236179-9fba6fdf-74d6-4a53-a573-a94c2ae4c99e.png)

4. OR, понадобилось 3 эпохи, на 4 уже вычислялось корректно.

![image](https://user-images.githubusercontent.com/113508468/205247003-a6dc1549-82f9-447d-9bf0-bfabe7230dc5.png)

```
  void Start () {
		Train(4);
		Debug.Log("Test 0 0: " + CalcOutput(0,0));
		Debug.Log("Test 0 1: " + CalcOutput(0,1));
		Debug.Log("Test 1 0: " + CalcOutput(1,0));
		Debug.Log("Test 1 1: " + CalcOutput(1,1));		
	}
```

5. AND, понадобилось 4 эпохи, на 5 уже вычислялось корректно.

![image](https://user-images.githubusercontent.com/113508468/205247775-dd8fc995-8049-4f56-8a95-0f8ea104fd4e.png)

```
	void Start () {
		Train(5);
		Debug.Log("Test 0 0: " + CalcOutput(0,0));
		Debug.Log("Test 0 1: " + CalcOutput(0,1));
		Debug.Log("Test 1 0: " + CalcOutput(1,0));
		Debug.Log("Test 1 1: " + CalcOutput(1,1));		
	}
```

6. NAND, понадобилось 5 эпох, на 6 уже вычислялось корректно.

![image](https://user-images.githubusercontent.com/113508468/205248146-4c805e8e-a5f2-49f2-98bd-b17132182c63.png)

```
	void Start () {
		Train(6);
		Debug.Log("Test 0 0: " + CalcOutput(0,0));
		Debug.Log("Test 0 1: " + CalcOutput(0,1));
		Debug.Log("Test 1 0: " + CalcOutput(1,0));
		Debug.Log("Test 1 1: " + CalcOutput(1,1));		
	}
```

7. XOR, даже спустя 100000 эпох так и не смог обучиться, поэтому некорректно выполняет вычисления.

![image](https://user-images.githubusercontent.com/113508468/205248535-cd0c4919-9009-44ef-9195-c6c4d0091cd5.png)

```
	void Start () {
		Train(10000);
		Debug.Log("Test 0 0: " + CalcOutput(0,0));
		Debug.Log("Test 0 1: " + CalcOutput(0,1));
		Debug.Log("Test 1 0: " + CalcOutput(1,0));
		Debug.Log("Test 1 1: " + CalcOutput(1,1));		
	}
```

## Задание 2
### Построить графики зависимости количества эпох от ошибки обучения. Указать от чего зависит необходимое количество эпох обучения

Ход работы:

1. Занес данные в google sheets и построил по ним график

![image](https://user-images.githubusercontent.com/113508468/205250851-4132b154-962d-4df6-a9ae-b9934616b847.png)

2. Количество эпох зависит от смещения и веса.

```
	double DotProductBias(double[] v1, double[] v2) 
	{
		if (v1 == null || v2 == null)
			return -1;
	 
		if (v1.Length != v2.Length)
			return -1;
	 
		double d = 0;
		for (int x = 0; x < v1.Length; x++)
		{
			d += v1[x] * v2[x];
		}

		d += bias; # Количество эпох зависит от bias
	 
		return d;
	}

	double CalcOutput(int i)
	{
		double dp = DotProductBias(weights,ts[i].input); # А так же от weights
		if(dp > 0) return(1);
		return (0);
	}
```

## Выводы

В первом задании Я познакомился с работой перцептрона, который вычисляет различные функции.
Во втором задании построил график зависимостей и выяснил от чего зависит количество эпох.

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
