# class HEX
```python
HEX("ffffff") -> HEX(color="#FFFFFF")
HEX("#FFFFFF").to_rgb() -> (255, 255, 255)
HEX("#3e3d3d").color -> '#3E3D3D'
HEX("#xxx") -> ValueError: Wrong color at '#xxx'
HEX("#QQQQQQ") -> ValueError: Wrong color at '#QQQQQQ'
```

# class RGB
```python
RGB(0, 0, 0) -> RGB(r=0, g=0, b=0)
RGB(255, 255, 255).to_hex(upper=True, hashtag=False) -> FFFFFF
RGB(30, 30, 30).color -> (30, 30, 30)
RGB(256, -2, 400) -> ValueError: Wrong color at (r=256, g=-2, b=400)
RGB(100, 100, 100) + RGB(30, 30, 30) -> RGB(r=65, g=65, b=65) # WARNING!!! Don't use this if you have more than 2 color

ColorConverter.mix_rgb(RGB(100, 100, 100), RGB(30, 30, 30), RGB(255, 255, 255)) -> RGB(r=128, g=128, b=128) # If you have more than 2 colors, use this.
```


<h2>Examples</h2>
<h3>Preview color</h3>

```python
from color_palette import Previewer, RGB

Previewer.preview(RGB(30, 30, 30))
```
<h3>Convert colors</h3>

```python
from color_palette import RGB, HEX, ColorConverter

print(ColorConverter.hex_to_rgb(HEX("#dd33bd"))) # RGB(r=221, g=51, b=189)
print(ColorConverter.rgb_to_hex(RGB(156, 48, 39))) # HEX(color=#9C3027)
```
<h3>Mix colors</h3>

```python
from color_palette import RGB, ColorConverter

print(ColorConverter.mix_rgb(RGB(100, 100, 100), RGB(255, 55, 88), RGB(79, 23, 54))) # RGB(r=144, g=59, b=80)
```
