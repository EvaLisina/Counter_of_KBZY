activities = {'сидячая': 1.2, 'низкая': 1.375, "средняя": 1.55, "высокая": 1.725}
def information():
  try:
    weight = float(input("Введите ваш вес цифрой: "))
    height = float(input("Введите ваш рост: "))
    nums = int(input("Введите ваш возраст: "))
    pol = input("Выберите ваш пол (м/ж): ")
    activ = input("Выберите вашу активность (сидячая, низкая, средняя, высокая): ")
  except ValueError:
    print("Введите подходящее значение!")
    
  calculate(weight, height, nums, pol, activ)

def calculate(w, h, n, p, a):
  if p == "м":
    all_m = (88.36 + (13.4 * w) + (4.8 * h) - (5.7 * n)) * activities[a]
    print(f'Ваша дневная норма калорий: {all_m}\n'
          f'Ваша дневная норма белков: {all_m / 100 * 25 / 4}\n'
          f'Ваша дневная норма жиров: {all_m / 100 * 15 / 9}\n'
          f"Ваша дневная норма углеводов: {all_m / 100 * 60 / 4}")
  elif p == "ж":
    all_w = (447.6  + (9.2 * w) + (3.1 * h) - (4.3 * n)) * activities[a]
    print(f'Ваша дневная норма калорий: {all_w}\n'
    f'Ваша дневная норма белков: {all_w / 100 * 25 / 4}\n'
    f'Ваша дневная норма жиров: {all_w / 100 * 25 / 4}\n'
    f"Ваша дневная норма углеводов: {all_w / 2}")

information()
