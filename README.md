# 🎛 glsl-noise-template-string

Use popular noise functions withing glsl written in JS Template-Strings. You do not need to add extra dependencies as this works with built-in JavaScript functionality. The package also has **TypeScript Support**.

This package is **still experimental**, so I am very happy if you report bugs or suggestions in the [issue section](https://github.com/s1gr1d/glsl-noise-template-string/issues).

## Usage

Import the functions you need, add them to the Template String and you can use them in your code.

```glsl
import { simplex3D, simplex4D } from 'glsl-noise-template-string'

const vertexShader = `
    ${simplex4D} 
	${simplex3D}
   
    varying vec2 vUv;
    uniform float time;
    
    void main() {
      vUv = uv;
      
      vec3 pos = position;
      pos += simplex4D(vec4(position, time));
           
      gl_Position = projectionMatrix * modelViewMatrix * vec4(pos, 1.0);
    }
`
```



## Available Functions

- perlin2D
- perlin3D
- simplex2D
- simplex3D
- simplex4D
- ... more to come ([add suggestion](https://github.com/s1gr1d/glsl-noise-template-string/issues/new))



## Upcoming Features

- [ ] Deterministic Randomness