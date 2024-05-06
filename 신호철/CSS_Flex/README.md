# Flex(Flexible Box)

기존의 `<table>`, `float`, `inline-block` 등의 방식 보다 쉽게 수평/수직 구성을 가능하게 해주는 속성

> 아주 간단한 예시  

```html
<div class="box-container">
   <div class="box"></div>
  <div class="box"></div>
  <div class="box"></div>
</div>
```

```css
/* display: flex; 주목! */
.box-container {
  display: flex;
}
```

또한 Flex는 하나의 container과 그 안에 있는 여러 item들로 구성되어 있으며,  
container와 item에 적용하는 속성이 구분되어 있음

![fc,fe](https://www.heropy.dev/postAssets/Ha29GI/flex-base.jpg)

## Flex Container

Flex Container에서 쓰이는 속성

|속성|의미|
|:--|:-----|
|`display`|Flex Container를 정의|
|`flex-flow`|flex-direction와 flex-wrap의 단축 속성|
|`flex-direction`|Flex Items의 주 축(Main Axis)을 설정|
|`flex-wrap`|Flex Items의 여러 줄 묶음(줄 바꿈) 설정|
|`justify-content`|주 축(Main Axis)의 정렬 방법을 설정|
|`align-content`|교차 축(Cross Axis)의 정렬 방법을 설정(2줄 이상)|
|`align-items`|교차 축(Cross Axis)에서 Items의 정렬 방법을 설정(1줄)|
|`gap`|각 아이템 사이의 간격을 설정|

### display

해당 태그를 flex container로 정의
> ex) display: 값;

|값|의미|
|:--|:-----|
|`flex`|container를 `block` 스타일로 설정|
|`inline-flex`|container를 `inline` 스타일로 설정|

**해당 속성은 item이 아닌 container 자체에 적용됨**

![display](https://www.heropy.dev/postAssets/Ha29GI/flex-display.jpg)

### flex-direction

Item들이 정렬될 주축(main-axis)을 지정
> ex) flex-direction: 주축;

|값|의미|
|:--|:-----|
|`row`|Item들을 수평축(좌->우)으로 표시 ***(기본값)***|
|`column`|Item들을 수직축(상->하)으로 표시|
|`row-reverse`|Item들을 수평축(우->좌)으로 표시|
|`column-reverse`|Item들을 (하->상)으로 표시|

![flex-direction](https://www.heropy.dev/postAssets/Ha29GI/flex-direction.jpg)

#### 주축(main-axis), 교차축(cross-axis)

주축(main-axis)과 수직인 교차축(cross-axis)이 존재

- 주축이 `row`(수평)일 시 교차축은 수직
- 주축이 `column`(수직)일 시 교차축은 수평

![ma,ca](https://www.heropy.dev/postAssets/Ha29GI/flex-direction-main-axis.jpg)

#### 시작점(flex-start), 끝점(flex-end)

주축 혹은 교차축이 시작하는 지점, 끝나는 지점을 지칭
축의 수직/수평 과 정방향/역방향 에 따라 달라짐

![ma-fs,fe](https://www.heropy.dev/postAssets/Ha29GI/flex-direction-main-start.jpg)
![ca-fs,fe](https://www.heropy.dev/postAssets/Ha29GI/flex-direction-cross-start.jpg)

### flex-wrap

Item들의 줄 묶음을 지정
> ex) flex-wrap: 줄묶음;

|값|의미|
|:--|:-----|
|`nowrap`|Item들을 한줄에 전부 표시 ***(기본값)***|
|`wrap`|Item들을 여러줄로 묶음|
|`wrap-reverse`|Item들을 여러줄로 묶되, 역방향으로 묶음|

![](https://www.heropy.dev/postAssets/Ha29GI/flex-wrap.jpg)

### flex-flow

`flex-direction`과 `flex-wrap`을 한번에 지정하는 단축 속성
> ex) flex-flow: 주축 줄묶음;

### justify-content

주축의 정렬방법을 지정
> ex) justify-content: 정렬방법;

|값|의미|
|:--|:-----|
|`flex-start`|Item들을 시작점으로 정렬 ***(기본값)***|
|`flex-end`|Item들을 끝지점으로 정렬|
|`center`|Item들을 중앙으로 정렬|
|`space-around`|각 Item 좌우 여백을 고르게 정렬|
|`space-between`|첫 Item은 시작점에, 끝 Item은 끝점에 정렬되고 나머지 여백으로 고르게 정렬|
|`space-evenly`|모든 여백을 고르게 정렬|

![](https://www.heropy.dev/postAssets/Ha29GI/flex-justify-content.jpg)

### align-content

교차축의 정렬방법을 지정
> ex) align-content: 정렬방법;

|값|의미|
|:--|:-----|
|`stretch`|Container의 교차축을 채우기 위해 Items의 크기를 늘림 ***(기본값)***|
|`flex-start`|Item들을 시작점으로 정렬|
|`flex-end`|Item들을 끝지점으로 정렬|
|`center`|Item들을 중앙으로 정렬|
|`space-around`|각 Item 좌우 여백을 고르게 정렬|
|`space-between`|첫 Item은 시작점에, 끝 Item은 끝점에 정렬되고 나머지 여백으로 고르게 정렬|
|`space-evenly`|모든 여백을 고르게 정렬|

![](https://www.heropy.dev/postAssets/Ha29GI/flex-align-content.jpg)

### align-items

교차축의 정렬방법을 지정 **(단 Item들이 두줄 이상일 경우, align-content가 stretch로 설정되어야 사용 가능)**
> ex) align-items: 정렬방법;

|값|의미|
|:--|:-----|
|`stretch`|Container의 교차축을 채우기 위해 Items의 크기를 늘림 ***(기본값)***|
|`flex-start`|Item들을 시작점으로 정렬|
|`flex-end`|Item들을 끝지점으로 정렬|
|`center`|Item들을 중앙으로 정렬|
|`baseline`|Item들을 문자 기준선에 정렬|

![](https://www.heropy.dev/postAssets/Ha29GI/flex-align-items.jpg)

### gap

각 아이템 사이의 간격을 지정(px, em등의 단위 사용)
> ex) gap: 간격;

## Flex Items

Flex Item에서 쓰이는 속성

|속성|의미|
|:--|:-----|
|`order`|Flex Item의 순서를 설정|
|`flex`|flex-grow, flex-shrink, flex-basis의 단축 속성|
|`flex-grow`|Flex Item의 증가 너비 비율을 설정|
|`flex-shrink`|Flex Item의 감소 너비 비율을 설정|
|`flex-basis`|Flex Item의 (공간 배분 전) 기본 너비 설정|
|`align-self`|교차 축(cross-axis)에서 Item의 정렬 방법을 설정|

### order

해당 Item 순서를 결정(숫자가 낮을 수록 앞에 배치)
> ex) order: 순서;

![](https://www.heropy.dev/postAssets/Ha29GI/flex-order.jpg)

### flex-grow

Item의 증가 너비 비율 조정 **(Item이 가변너비여야 함)**

> ex) flex-grow: 증가너비;

![](https://www.heropy.dev/postAssets/Ha29GI/flex-grow.jpg)

### flex-shrink

Item의 증가 너비 비율 조정 **(Item이 가변너비여야 함)**

> ex) flex-shrink: 감소너비;

**Container의 너비가 줄어 Items의 너비에 영향을 미칠 경우, 영향을 미치기 시작한 지점부터**  
**줄어든 거리 만큼 감소 너비 비율에 맞게 Item의 너비가 줄어듬**

![](https://www.heropy.dev/postAssets/Ha29GI/flex-shrink.jpg)

### flex-basis

Item의 기본 너비를 설정(기본값: `auto` / px, em등의 단위 사용)  
*flex-grow, flex-shrink보다 먼저 계산*

> ex) flex-basis: 기본너비;

![](https://www.heropy.dev/postAssets/Ha29GI/flex-basis.jpg)

### align-self

교차축에서 개별 Item의 정렬방법 지정  
*align-items 보다 우선순위 높음*

> ex) align-self: stretch;

![](https://www.heropy.dev/postAssets/Ha29GI/flex-align-self.jpg)
