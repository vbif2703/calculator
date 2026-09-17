def convert_bytes():
    # Словарь единиц измерения (множители относительно байт)
    units = {
        'b': 1,
        'kb': 1024,
        'mb': 1024 ** 2,
        'gb': 1024 ** 3,
        'tb': 1024 ** 4
    }

    available_units = ", ".join(units.keys())
    print(f"Доступные единицы: {available_units}\n")

    # 1. Ввод количества
    try:
        amount = float(input("Введите количество: "))
    except ValueError:
        print("Ошибка: введите число!")
        return

    # 2. Выбор исходной единицы (ИЗ ЧЕГО переводим)
    from_unit = input("Перевести ИЗ : ").strip().lower()
    if from_unit not in units:
        print(f"Ошибка: такой единицы нет. Выберите из: {available_units}")
        return

    # 3. Выбор целевой единицы (ВО ЧТО переводим)
    to_unit = input("Перевести В : ").strip().lower()
    if to_unit not in units:
        print(f"Ошибка: такой единицы нет. Выберите из: {available_units}")
        return

    # 4. Расчет через базовую единицу (байты)
    bytes_amount = amount * units[from_unit]
    result = bytes_amount / units[to_unit]

    # 5. Вывод результата
    print(f"Результат: {amount} {from_unit.upper()} = {round(result, 4)} {to_unit.upper()}")


# Запуск
if __name__ == "__main__":
    convert_bytes()

convert_bytes()
