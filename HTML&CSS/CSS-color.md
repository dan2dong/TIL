# CSS-color

## RGBA Colors

- rgba(red, green, blue, alpha)

```CSS
#p1 {background-color: rgba(255, 0, 0, 0.3);}  /* red with opacity */
#p2 {background-color: rgba(0, 255, 0, 0.3);}  /* green with opacity */
#p3 {background-color: rgba(0, 0, 255, 0.3);}  /* blue with opacity */
```

## HSL Colors

Hue : 색상</br>
Saturation : 채도</br>
Lightness : 명도
</br>

### Hue(색상)

</br>
0 (or 360) is red</br>
120 is green</br>
240 is blue
</br>

### Saturation(채도)

</br>
0 ~ 100 % (% 단위 필수)</br>
0%는 음영, 100%는 컬러 최대치

### lightness (명도)

</br>
0 ~ 100 %  (% 단위 필수)</br>
0%는 검은색, 50 %는 보통, 100%는 흰색

```CSS
#p1 {background-color: hsl(120, 100%, 50%);}  /* green */
#p2 {background-color: hsl(120, 100%, 75%);}  /* light green */
#p3 {background-color: hsl(120, 100%, 25%);}  /* dark green */
#p4 {background-color: hsl(120, 60%, 70%);}   /* pastel green */
```
