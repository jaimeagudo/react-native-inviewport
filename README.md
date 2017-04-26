# react-native-inviewport
It detects if the component is visible within device viewport. Performance wise notice there is a watch checking every 100ms

Originally based off: https://github.com/joshwnj/react-visibility-sensor with some fixes

<H2>Install</H2>

~~npm install react-native-inviewport@latest --save~~

Copy index.js to your project for now, the npm is obsolte

<H2>Example Usage</H2>

Assuming you already setup your component, here's a quick example.

```
  onViewPortToggle(isVisible){
     this.setState({ isVisible })
     console.log('My children are rendering while %s', isVisible ? 'visible' : 'hidden')
  }

render() {
  return (
  <View style={{flex: 1, height: 200}}>
      <ScrollView style={{flex: 1}}>
        <InViewPort onChange={this.onViewPortToggle}>
          <View style={{flex: 1, height: 200, backgroundColor: 'blue'}}>
            <Text>I am hidden sometimes</Text>
          </View>
        </InViewPort>

          <View style={{flex: 1, height: 400, backgroundColor: 'green'}}>
            <Text>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed eiusmod tempor incidunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquid ex ea commodi consequat. Quis aute iure reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint obcaecat cupiditat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum</Text>
          </View>
      </ScrollView>

      <Text>{ 'My scrolled component is' + (this.state.isVisible ? 'visible' : 'hidden')}</Text>
  </View>
  );
}
```
