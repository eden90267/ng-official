#  顯示數據

最典型是 HTML 模板的控件綁定到 Angular 組件的屬性。

## 使用插值表達式顯示組件屬性

最簡單方式，插值表達式 interpolation 綁定屬性名。

```html
{{myHero}}
```

## 內聯 (inline) 模板還是模板文件

- template
- templateUrl

取決個人喜好、具體狀況和組織級策略。

## 使用構造函數函式變量初始化？

出自應用是否剪短。

## 使用 ngFor 顯示資料屬性

```javascript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <h1>{{title}}</h1>
    <h2>My favorite hero is: {{myHero}}</h2>
    <p>Heroes:</p>
    <ul>
      <li *ngFor="let hero of heroes">
        {{hero}}
      </li>
    </ul>
  `
})
export class AppComponent {
  title = 'Tour of Heroes';
  heroes = ['Windstorm', 'Bombasto', 'Magneta', 'Tornado'];
  myHero = this.heroes[0];
}
```

## 為數據創建一個類

用來為組件描述模型數據並顯示模型的屬性

```shell
$ ng g class hero
```

## 透過 NgIf 進行條件顯示

透過添加和刪除方式處理元素。這會提高性能，避免不必要渲染。