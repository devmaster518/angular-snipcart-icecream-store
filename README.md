# angular-snipcart-icecream-store

> Angular IceCream eStore website using `Snipcart` eCommerce Platform

Because summer is coming in Canada and its been quite a long year, I wanted to replenish my youth memories and make an **REPLENISHING ICE CREAM STORE**!

## Getting Started

![Ice Cream eStore](screenshots/ngapp.png)

```yml
node.js: ^14.21.3
angular/cli: ~11.2.12
```

## How To Run

```yml
# install dependencies
$ npm i

# ng serve
$ npm start
```

Visit http://localhost:4200/

## Create Components

Later in the tutorial, we will use a full InMemoryDbService. For now, let's do something simple and simply create a `mock-products.ts` file in our root component:

```ts
import { Product } from "./core/product";
import { Size } from "./core/size";

export const PRODUCTS: Product[] = [
  {
    id: 1,
    name: "Ice Cream",
    imageUrls: ["../assets/ice-cream-prune.svg", "../assets/ice-cream-cherry.svg", "../assets/ice-cream-squash.svg"],
    price: 10,
    flavors: [
      { name: "prune", color: "#5A188E" },
      { name: "squash", color: "#F88532" },
      { name: "cherry", color: "#E91E63" },
    ],
    sizes: [Size.SMALL, Size.MEDIUM, Size.LARGE],
  },
  {
    id: 2,
    name: "Popsicle",
    imageUrls: ["../assets/popsicle-lime.svg", "../assets/popsicle-lettuce.svg", "../assets/popsicle-cherry.svg"],
    price: 8,
    flavors: [
      { name: "lime", color: "#00CACA" },
      { name: "lettuce", color: "#80DC0B" },
      { name: "cherry", color: "#E91E63" },
    ],
    sizes: [Size.SMALL, Size.LARGE],
  },
];
```

```ts
// core/product.ts

import { Flavor } from "./flavor";
import { Size } from "./size";

export interface Product {
  id: number;
  name: string;
  imageUrls: string[];
  price: number;
  flavors: Flavor[];
  sizes: Size[];
}
```

```ts
// core/flavor.ts
export interface Flavor {
  name: string;
  color: string;
}
```

```ts
// core/size.ts
export enum Size {
  SMALL = "small",
  MEDIUM = "medium",
  LARGE = "large",
}
```

```ts
// homepage.component.ts

@Component({
  selector: "app-homepage",
  templateUrl: "./homepage.component.html",
  styleUrls: ["./homepage.component.scss"],
})
export class HomepageComponent {
  title = "Infinite summer ice cream store";
  subtitle = "Which one do you want?";
}
```

```html
<!-- homepage.component.html -->
<div class="header" fxLayout="column" fxLayoutAlign="center center">
  <h1 class="jumbo">{{ title }}</h1>
  <h2>{{ subtitle }}</h2>
</div>
```

```html
<!-- app.component.html -->

<app-homepage></app-homepage>
```

```ts
import { PRODUCTS } from "../mock-products";
```

```ts
export class ProductsComponent implements OnInit {
  products = PRODUCTS;
}
```

**etc.**

---

## Snipcart login

![Snipcart Login](screenshots/snipcart_login.png)

&copy; 2024 @codeguru827

All rights reserved.
