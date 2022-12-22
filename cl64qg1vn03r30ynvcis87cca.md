# [CSS] overflow / text-overflow

# overflow : 넘처 흐르다

위의 사진처럼 맥주병의 크기는 한계가 있는데 맥주가 넘처 흐를때, 같은 의미로 할당된 공간에 비해 content의 내용이 넘처 흐를 때, 공간을 visually 늘리는 대신 overflow라는 property를 사용해서 할당된 공간을 보이지 않게 늘려줄 수 있다.

인스타그램을 클론코딩하는 과제를 진행하면서, content의 내용이 많을 때 '...'으로 표시되야 하는 경우가 있었다.

구글링 해보며 `text-overflow`를 알게 되었고 적용해 보았다.

> The text-overflow CSS property sets how hidden overflow content is signaled to users. It can be clipped, display an ellipsis ('…'), or display a custom string. (src from mdn)

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1658994015106/8Xkjtxcda.png align="left")

### 직접 시도해 보며 알게 된 사실
- `<p>`는 `text-overflow`가 적용되지만 <span>은 적용되지 않는다. display의 영향을 받는 듯 하다. display가 `inline`인 경우 사용 불가. 굳이 `<span>`에 사용하고 싶으면 `<span>`을 `<div>`로 감싸주면 가능하다.

- 'text-overflow`에 필수로 넣어주어야 하는 properties => (overflow: hidden; width: ...px; white-space: nowrap;)
```
//example
.lastUpdated {
    text-overflow: ellipsis;
    overflow: hidden;
    width: 120px;
    white-space: nowrap;
}
```
