# shapes, SDFs

## circles

$$
x^2 + y^2 = r^2 \\
x^2 + y^2 - r^2 = 0
$$

```glsl
vec3 sdfCircle(vec2 uv, float r, vec2 offset)
{
    float x = uv.x - offset.x;
    float y = uv.y - offset.y;

    float d = length(vec2(x, y)) - r;

    return d > 0. ? vec3(1.) : vec3(0., 0., 1.);
}
```

## squares

$$
max(abs(x), abs(y)) = r \\
max(abs(x), abs(y)) - r = 0
$$

```glsl
vec3 sdfSquare(vec2 uv, float size, vec2 offset) 
{
    float x = uv.x - offset.x;
    float y = uv.y - offset.y;

    float d = max(abs(x), abs(y)) - size;

    return d > 0. ? vec3(1.) : vec3(0., 0., 1.);
}

```
