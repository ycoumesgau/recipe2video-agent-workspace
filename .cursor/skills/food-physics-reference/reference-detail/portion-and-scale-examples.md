# Portion and Scale Examples

Use these examples to avoid unrealistic size drift in prompts.

## Arancini

- preferred: `small arancini balls, about 3-4 cm diameter each, bite-size, fitting in one palm`;
- include count when visible: `12 arancini balls`;
- negative: `not soccer-ball sized`.

## Entremets

- preferred: `single entremets ring, about 18-20 cm diameter and 4-6 cm tall`;
- if smaller format: `individual entremets, 7-8 cm diameter`;
- negative: `not oversized like a full tray cake`.

## Choux Ring / Paris-Brest

- preferred: `one crown made of separate choux domes, each about 3-4 cm wide`;
- include topology: `separate domes touching each other`;
- negative: `not a smooth single donut ring`.

## Burger / Sandwich / Bun-like Items

- preferred: `handheld size, around 9-11 cm diameter`;
- keep hand relation explicit: `proportional to two hands holding it`;
- negative: `not plate-sized giant bun`.

## Garnish and Toppings

- preferred: `fine garnish visible but secondary to main food geometry`;
- keep ratio explicit: `toppings occupy less than 15% of visible surface`;
- negative: `not dense confetti-like full coverage unless intended`.

## Prompt Pattern

Use this sentence pattern in prompts:

`Scale lock: [numeric size], [relative kitchen anchor], [count/topology]. Not [oversized interpretation].`
