# Homework_13.2



class Counter:
    def __init__(self, current=1, min_value=0, max_value=10):
        # Инициализация начального, минимального и максимального значений
        self.current = current
        self.min_value = min_value
        self.max_value = max_value

    def set_current(self, start):
        # Установка текущего значения
        self.current = start

    def set_max(self, max_max):
        # Установка максимального значения
        self.max_value = max_max

    def set_min(self, min_min):
        # Установка минимального значения
        self.min_value = min_min

    def step_up(self):
        # Увеличение значения на 1 с проверкой на достижение максимума
        if self.current + 1 > self.max_value:
            raise ValueError("Достигнут максимум")
        self.current += 1

    def step_down(self):
        # Уменьшение значения на 1 с проверкой на достижение минимума
        if self.current - 1 < self.min_value:
            raise ValueError("Достигнут минимум")
        self.current -= 1

    def get_current(self):
        # Возврат текущего значения
        return self.current


# Пример использования
counter = Counter()

# Установка начального значения
counter.set_current(7)

# Увеличиваем значение
counter.step_up()
counter.step_up()
counter.step_up()
print("Текущее значение:", counter.get_current())  # Ожидается 10

try:
    counter.step_up()  # Это должно вызвать ValueError
except ValueError as e:
    print(e)

# Уменьшаем значение
counter.set_min(7)
counter.step_down()
counter.step_down()
counter.step_down()
print("Текущее значение:", counter.get_current())  # Ожидается 7

try:
    counter.step_down()  # Это должно вызвать ValueError
except ValueError as e:
    print(e)
