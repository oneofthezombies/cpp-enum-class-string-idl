# cpp-enum-class-string-idl

```shell
python3 -m cpp_enum_class_string_idl MyEnums.yaml
```

```yaml
# MyEnums.yaml
interfaces:
  - MyEnum.yaml
  - Directions.yaml
```

```yaml
# MyEnum.yaml
name: MyEnum
type: int
values:
  - Value0
  - Value1
```

```yaml
# Directions.yaml
name: Directions
type: int
values:
  - Left
  - Right
```

```cpp
// MyEnum.h
#pragma once

/*
 * generated code from cpp-enum-class-string-idl
 */

enum class MyEnum : int {
    Value0,
    Value1,
    Count
};

const char* enum_to_string(const MyEnum value);
```

```cpp
#include "MyEnum.h"

/*
 * generated code from cpp-enum-class-string-idl
 */

const char* _MyEnum[] = {
    "Value0",
    "Value1"
};

const char* enum_to_string(const MyEnum value) {
    if (MyEnum::Count == value) {
        return "";
    }

    return _MyEnum[static_cast<int>(value)];
}
```
