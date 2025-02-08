# time_line_example
---
## css Properties Elements.

1) backdrop-filter:- it applies graphical Effects(like blur or color Adjustments) to the area behind a semi-transparant element. 

* mostly use to create frosted glass effect 
> if you are using background color then it's transparency Should be less then 50% then drop filter will work properly.

>> example :-
```
.element
{
    backdrop-filter:blur(10px);
}
``` 
we can use brightness, contrast,Grayscale,sepia,saturate,Hue Rotate or all filter at once.

```
backdrop-filter: blur(5px) brightness(120%) contrast(150%);

```
