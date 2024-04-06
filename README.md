activities = {'сидячая': 1.2, 'низкая': 1.375, "средняя": 1.55, "высокая": 1.725}

def information():
  try:
    weight = float(input("Введите ваш вес: "))
    height = float(input("Введите ваш рост: "))
    nums = int(input("Введите ваш возраст: "))
    pol = input("Выберите ваш пол (м/ж): ")
    activ = input("Выберите вашу активность (сидячая, низкая, средняя, высокая): ")
    want = input('Что вы хотите сделать? (похудеть, поддерживать вес, набрать вес): ')
  except ValueError:
    print("Введите подходящее значение!")
    information()
    

  calculate(weight, height, nums, pol, activ, want)

def calculate(w, h, n, p, a, wnt):
  all_m = (88.36 + (13.4 * w) + (4.8 * h) - (5.7 * n)) * activities[a]
  all_w = (447.6  + (9.2 * w) + (3.1 * h) - (4.3 * n)) * activities[a]
  if p == "м" and wnt == "поддерживать вес":
    print(f'Ваша дневная норма калорий: {round(all_m, 2)}\n'
      f'Ваша дневная норма белков: {round(all_m / 100 * 25 / 4, 2)}\n'
      f'Ваша дневная норма жиров: {round(all_m / 100 * 15 / 9, 2)}\n'
      f"Ваша дневная норма углеводов: {round(all_m / 100 * 60 / 4, 2)}")
  elif p == "м" and wnt == "похудеть":
    new_c = round(all_m, 2) - round(all_m / 5, 2) 
    print(f'Ваша дневная норма калорий: {new_c}\n'
      f'Ваша дневная норма белков: {round(new_c / 100 * 25 / 4, 2)}\n'
      f'Ваша дневная норма жиров: {round(new_c / 100 * 15 / 9, 2)}\n'
      f"Ваша дневная норма углеводов: {round(new_c / 100 * 60 / 4, 2)}")
  elif p == "м" and wnt == "набрать вес":
    new_c = round(all_m, 2) + round(all_m / 5, 2) 
    print(f'Ваша дневная норма калорий: {round(new_c, 2)}\n'
      f'Ваша дневная норма белков: {round(new_c / 100 * 25 / 4, 2)}\n'
      f'Ваша дневная норма жиров: {round(new_c / 100 * 15 / 9, 2)}\n'
      f"Ваша дневная норма углеводов: {round(new_c / 100 * 60 / 4, 2)}")
  elif p == "ж" and wnt == "поддерживать вес":
    print(f'Ваша дневная норма калорий: {round(all_w, 2)}\n'
    f'Ваша дневная норма белков: {round(all_w / 100 * 25 / 4, 2)}\n'
    f'Ваша дневная норма жиров: {round(all_w / 100 * 25 / 9, 2)}\n'
    f"Ваша дневная норма углеводов: {round(all_w / 100 * 50/ 4, 2)}")
  elif p == "ж" and wnt == "похудеть":
    new_c = round(all_w, 2) - round(all_w / 5, 2) 
    print(f'Ваша дневная норма калорий: {round(new_c, 2)}\n'
    f'Ваша дневная норма белков: {round(new_c / 100 * 25 / 4, 2)}\n'
    f'Ваша дневная норма жиров: {round(new_c / 100 * 25 / 9, 2)}\n'
    f"Ваша дневная норма углеводов: {round(new_c / 100 * 50/ 4, 2)}")
  elif p == "ж" and wnt == "набрать вес":
    new_c = round(all_w, 2) + round(all_w / 5, 2) 
    print(f'Ваша дневная норма калорий: {round(new_c, 2)}\n'
    f'Ваша дневная норма белков: {round(new_c / 100 * 25 / 4, 2)}\n'
    f'Ваша дневная норма жиров: {round(new_c / 100 * 25 / 9, 2)}\n'
    f"Ваша дневная норма углеводов: {round(new_c / 100 * 50/ 4, 2)}")

information()
