# How to solve "RNSScreenStackHeaderConfig" was not found in the UIManager when running android app

This article describe how to solve problem when you install and configure `react-native-navigation` on your ReactNative project.

## Correct install

1. Install dependencies -> `npm install @react-navigation/native`
2. Install more -> `npm install react-native-screens react-native-safe-area-context`
3. **(OPTIONAL)** If you use iOS -> `npx pod-install ios`
4. Search your file: `android/app/src/main/java/<your package name>/MainActivity.java` and add following code on Java class:
```
@Override
protected void onCreate(Bundle savedInstanceState) {
  super.onCreate(null);
}
```
5. Then include following line in **MainActivity.java**:
```
import android.os.Bundle;
```

## Fix "RNSScreenStackHeaderConfig" was not found in the UIManager

1. Kill **Metro** and clean gradle build (it might take a minute or two):
```
cd android
.\gradlew clean
```
2. Start Metro and clear cache:
```
npm start --reset-cache
```
3. Recompile and install APK
```
npm run android
```

## Using native-stack

1. Install -> `npm install @react-navigation/native-stack`
2. Add following code in your component:
```
import { NavigationContainer } from '@react-navigation/native';
import { createNativeStackNavigator } from '@react-navigation/native-stack';
```
3. Example how to use:
```
const HomeScreen: () => Node = ({ navigation }) => {
    return (
        <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
        <Text>Home Screen</Text>
        </View>
  );
}

const Stack = createNativeStackNavigator();

const App = () => Node = ({ navigation }) => {
  return (
    <NavigationContainer>
      <Stack.Navigator>
        <Stack.Screen name="Home" component={HomeScreen} />
      </Stack.Navigator>
    </NavigationContainer>
  );
}

export default App;
```