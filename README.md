# react-native-actionsheet
Cross platform ActionSheet. This component implements a custom ActionSheet  and provides the same way to drawing it on the defferent platforms(iOS and Android). Actually, In order to keep the best effect, it still uses the ActionSheetIOS on iOS.

## 应用场景
- 开发中常用到：比如：选择相册，选择拍照等，这个底部弹出框选择，我们称之为 action sheet动作面板  
## Effect Picture
  - 动作面板效果
  
<a><img width="200" src="./actionSheet.png"></a>


## Install

```
npm install react-native-actionsheet --save
```

## Usage

```js
import ActionSheet from 'react-native-actionsheet'

class Demo extends React.Component {
  showActionSheet = () => {
    this.ActionSheet.show()
  }
  render() {
    return (
      <View>
        <Text onPress={this.showActionSheet}>Open ActionSheet</Text>
        <ActionSheet
          ref={o => this.ActionSheet = o}
          title={'Which one do you like ?'}
          options={['Apple', 'Banana', 'cancel']}
          cancelButtonIndex={2}
          destructiveButtonIndex={1}
          onPress={(index) => { /* do something */ }}
        />
      </View>
    )
  }
}
```


### Use ActionSheetCustom directly

so you can customize option and title

```js
import { ActionSheetCustom as ActionSheet } from 'react-native-actionsheet'

const options = [
  'Cancel', 
  'Apple', 
  <Text style={{color: 'yellow'}}>Banana</Text>,
  'Watermelon', 
  <Text style={{color: 'red'}}>Durian</Text>
]

class Demo extends React.Component {
  showActionSheet = () => {
    this.ActionSheet.show()
  }
  render() {
    return (
      <View>
        <Text onPress={this.showActionSheet}>Open ActionSheet</Text>
        <ActionSheet
          ref={o => this.ActionSheet = o}
          title={<Text style={{color: '#000', fontSize: 18}}>Which one do you like?</Text>}//最上面的标题
          options={options}//可以选择的选项
          cancelButtonIndex={0}//取消的位置
          destructiveButtonIndex={4}//默认选择的选项
          onPress={(index) => { /* do something */ }}
        />
      </View>
    )
  }
}
```

### How to redesign style ?

The style of ActionSheet is defined in [lib/styles.js](https://github.com/beefe/react-native-actionsheet/blob/master/lib/styles.js). We can pass the `styles` prop to cover default style. See [Example](https://github.com/beefe/react-native-actionsheet/blob/master/example/app/ExampleB.js#L48) .

```javascript
// example

const styles = {
  titleBox: {
    background: 'pink'
  },
  titleText: {
    fontSize: 16,
    color: '#000'
  }
}

<ActionSheet
  ...
  styles={styles}
/>
```

## Props

https://github.com/beefe/react-native-actionsheet/blob/master/lib/options.js

<table>
    <tr>
        <th>Prop name</th>
        <th>Desciption</th>
        <th>Type</th>
        <th>Default</th>
    </tr>
    <tr>
        <td>title</td>
        <td></td>
        <td>PropTypes.string or PropTypes.element</td>
        <td></td>
    </tr>
    <tr>
        <td>message</td>
        <td></td>
        <td>PropTypes.string or PropTypes.element</td>
        <td></td>
    </tr>
    <tr>
        <td>options</td>
        <td></td>
        <td>PropTypes.arrayOf([PropTypes.string, PropTypes.element])</td>
        <td></td>
    </tr>
    <tr>
        <td>tintColor</td>
        <td></td>
        <td>PropTypes.string</td>
        <td></td>
    </tr>
    <tr>
        <td>cancelButtonIndex</td>
        <td></td>
        <td>PropTypes.number</td>
        <td></td>
    </tr>
    <tr>
        <td>destructiveButtonIndex</td>
        <td></td>
        <td>PropTypes.number</td>
        <td></td>
    </tr>
    <tr>
        <td>onPress</td>
        <td></td>
        <td>PropTypes.func</td>
        <td>(index) => {}</td>
    </tr>
    <tr>
        <td>styles</td>
        <td>only for ActionSheetCustom</td>
        <td></td>
        <td>{}</td>
    </tr>
</table>
