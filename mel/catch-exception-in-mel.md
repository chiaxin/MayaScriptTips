# How to catch exception in MEL

## We can use "catch" command

```mel
if ( catch(`setAttr "simpleShader.color" 0.5 0.5 0.5`) )
    print("Failed to set simpleShader color!\n");
else
    print("Set simpleShader color successiful!\n");
```

+ If "catch" command got a error expression, it will return Ture.
+ So we must write failed message in if block
+ And we write success message in else block
+ If your express (message) only have one line, brace {} could be ignored.