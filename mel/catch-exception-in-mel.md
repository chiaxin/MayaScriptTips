# How to catch exception in MEL

## MEL has no exception character

## We can use "catch" command

```mel
if (catch(`setAttr "simpleShader.color" 0.5 0.5 0.5`))
    print("Failed to set simpleShader color!\n");
else
    print("Set simpleShader color successful!\n");
```

## Or use "catchQuiet" command

```mel
if (catchQuiet(`setAttr "simpleShader.color" 0.5 0.5 0.5`))
    print("Failed to set simpleShader color!\n");
else
    print("Set simpleShader color successful!\n");
```

The difference with `catch` is `catchQuiet` suppresses warnings and errors.

---

+ If "catch" command got a error expression, it will return `True`.
+ So we must write failed message in if block
+ And we write success message in else block
+ If your expression only have one line, brace {} could be ignored.