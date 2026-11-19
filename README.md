# Release Notes — v1.1.0

## Added
- Додано спеціальний базовий тариф на доставку для міста Kyiv у розмірі 80.0.
- Додано явний параметр ставки податку tax_rate (зі значенням за замовчуванням 0.20) у функцію process_standard_invoice.

## Changed
- Коефіцієнт вартості доставки за кілограм ваги збільшено з 12.0 до 15.0.
- Виконано повний архітектурний рефакторинг модуля: здійснено перехід від Common, Stamp та Control Coupling до еталонного Data Coupling.

## Breaking Changes
- Видалено глобальну змінну GLOBAL_TAX_RATE.
- Видалено функцію process_invoice із керуючим прапорцем mode_flag; її замінено на дві спеціалізовані функції: process_standard_invoice та process_tax_exempt_invoice.
- Змінено сигнатуру функції calculate_delivery_cost та функцій обробки рахунків: замість об'єкта CustomerProfile тепер передається виключно рядок city.
