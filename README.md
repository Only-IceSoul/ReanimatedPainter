# Reanimated Painter

Make sure you have reanimated and [Painter](https://github.com/Only-IceSoul/react-native-painter) installed

## Getting started

`$ yarn add reanimated-painter`



## Usage
```javascript
import AnimatedPainter, {getAnimatedProps } from 'reanimated-painter';
import Animated, {useAnimatedProps,useAnimatedReaction } from "react-native-reanimated";

  const theta = useSharedValue(0)

  const [animatedProps,setAnimatedProps] = getAnimatedProps<any>({
      //initial props web
  },useAnimatedProps(() => {
    return {
        //rotation
      rot: toDegrees(theta.value), 
    };
  }))

   if(Platform.OS === "web" ){
     useAnimatedReaction(()=>theta.value,(v)=>{
        runOnJS(setAnimatedProps!)({rot:toDegrees(v)})
     },[])
  }

      <AnimatedPainter.Circle
        animatedProps={animatedProps}
        />

```
