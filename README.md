# python 生成随机验证码图片

> 需要的pip包：pillow

```py

    from PIL import Image,ImageDraw,ImageFont
    import random

    img1 = Image.new(
        mode = "RGB",
        size = (120,30),
        color = (255,255,255)
    )

    # 实例化一只画笔
    draw1 = ImageDraw.Draw(img1,mode="RGB")

    font1 = ImageFont.truetype("Starn___.TTF", 28)

    arr = []

    for i in range(5):
        char1 = random.choice([chr(random.randint(65,90)), str(random.randint(0,9))])
        color1 = (random.randint(0,255), random.randint(0,255),random.randint(0,255))

        draw1.text([i*24+2,5],char1,color1,font=font1)

        arr.append(char1)

    with open("pic.png", "wb") as f:
        img1.save(f,format = "png")

    print(arr)

    str = "".join(arr)

    print(str)

    img1.show()


```
