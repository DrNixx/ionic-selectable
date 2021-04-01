[npm-url]: https://npmjs.org/package/@ionic-selectable/core
[npm-image]: https://img.shields.io/npm/v/@ionic-selectable/core.svg
[dm-image]: https://img.shields.io/npm/dm/@ionic-selectable/core.svg
[dt-image]: https://img.shields.io/npm/dt/@ionic-selectable/core.svg

# Ionic Selectable

[![npm][npm-image]][npm-url]
[![npm][dt-image]][npm-url]
[![npm][dm-image]][npm-url]

[Demo](https://stackblitz.com/edit/ionic-selectable-basic?file=pages/home/home.html) | [Features](#features) | [Getting started](#getting-started) | [FAQ](../../wiki#faq) | [Docs](../../wiki)

An Ionic component similar to [Ionic Select](https://ionicframework.com/docs/api/components/select/Select/), that allows to search items, including async search, infinite scrolling and more.

## `@ionic-selectable/core` for Vanilla JS
## `@ionic-selectable/angular` for Angular
- Made with stencil
- Web components
- Suport for Vainilla JS
- Suport for Angular
- Other frameworks support is coming!!!

![iOS Demo](images/demo.gif)

# Contents

- [Demo](https://stackblitz.com/edit/ionic-selectable-basic?file=pages/home/home.html)
- [Features](#features)
- [Getting started](#getting-started)
- [Supported Ionic versions](#supported-ionic-versions)
- [FAQ](../../wiki#faq)
- [Docs](../../wiki)
- [Theming](../../wiki#theming)

## Supported Ionic versions

- Ionic 5 (>=5.0.0) alpha

## Supported previus Ionic versions
- Ionic 3 (3.6.0 - 3.9.2) [ionic-selectable](https://www.npmjs.com/package/ionic-selectable)
- Ionic 4 (>=4.0.0) [ionic-selectable](https://www.npmjs.com/package/ionic-selectable)
## Features

- [Single selection](https://stackblitz.com/edit/ionic-selectable-basic?file=pages/home/home.html)
- [Multiple selection](../../wiki#ismultiple)
- [Search items](https://stackblitz.com/edit/ionic-selectable-basic?file=pages/home/home.html)
- [Search items asynchronously](https://stackblitz.com/edit/ionic-selectable-on-search?file=pages/home/home.html)
- [Search by several item fields](https://stackblitz.com/edit/ionic-selectable-on-search?file=pages/home/home.html)
- [Forms](https://stackblitz.com/edit/ionic-selectable-form-control?file=pages/home/home.html)
- [InfiniteScroll](https://stackblitz.com/edit/ionic-selectable-infinite-scroll?file=pages/home/home.html)
- [VirtualScroll](https://stackblitz.com/edit/ionic-selectable-virtual-scroll?file=pages/home/home.html)
- [Templates](../../wiki#templates)
- [Grouping items](../..//wiki#grouping)
- [Editing, adding and deleting items](../../wiki#editing)
- [Disabling items](../../wiki#disableditems)

## Getting started

1. Install it.

```
npm install @ionic-selectable/core --save # only for vanilla js
npm install @ionic-selectable/angular --save # only for angular
```

2. Import it.  
   First, import `IonicSelectableModule` to your `app.module.ts` that is normally located in `src\app\app.module.ts`.

```
import { IonicSelectableModule } from 'ionic-selectable';

@NgModule({
  imports: [
    IonicSelectableModule
  ]
})
export class AppModule { }

```

**Note:** Additionally, if you use Ionic 3+ you might be as well using lazy loaded pages. Check if your pages have a module file, for example, `home.module.ts`, and if they do then import `IonicSelectableModule` to each page module too.

```
import { IonicSelectableModule } from 'ionic-selectable';
import { HomePage } from './home';

@NgModule({
  declarations: [
    HomePage
  ],
  imports: [
    IonicPageModule.forChild(HomePage),
    IonicSelectableModule
  ]
})
export class HomePageModule { }

```

3. Add it to template.

```
<ion-item>
  <ion-label>Port</ion-label>
  <ionic-selectable
    [(ngModel)]="port"
    [items]="ports"
    itemValueField="id"
    itemTextField="name"
    [canSearch]="true"
    (onChange)="portChange($event)">
  </ionic-selectable>
</ion-item>
```

4. Configure it.

```
import { IonicSelectableComponent } from 'ionic-selectable';

class Port {
  public id: number;
  public name: string;
}

@Component({ ... })
export class HomePage {
  ports: Port[];
  port: Port;

  constructor() {
    this.ports = [
      { id: 1, name: 'Tokai' },
      { id: 2, name: 'Vladivostok' },
      { id: 3, name: 'Navlakhi' }
    ];
  }

  portChange(event: {
    component: IonicSelectableComponent,
    value: any
  }) {
    console.log('port:', event.value);
  }
}
```

5. Enjoy it 😉
6. Check out [live demos](https://stackblitz.com/@eakoriakin) to see what it is capable of.  
   Also, explore the [docs](../../wiki) and [FAQ](../../wiki#faq) to learn more about its features.

## Development

For contribution and delevopment please refer to [Contribution](../../wiki/Contribution).

## Share it

If you find this component useful, please star the [repo](https://github.com/eakoriakin/ionic-selectable) to let others know that it's reliable. Also, share it with friends and colleagues who might find it useful as well. Thank you 😄
