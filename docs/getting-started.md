Getting started
===============

Adding the dependency
----------------------

To use this library in a Maven project, add the following to your `pom.xml`:

```xml

<dependency>
    <groupId>nl.datastations</groupId>
    <artifactId>dans-jackson-converter-lib</artifactId>
    <version>{version}</version> <!-- <=== FILL LIBRARY VERSION TO USE HERE -->
</dependency>
```

Using a converter
------------------

The converters in this library are used on fields annotated with Jackson's `@JsonDeserialize` or `@JsonSerialize`. For example, `StringByteSizeConverter`
converts a human-readable byte size, such as `"1MB"`, into a `long`.

```java
import com.fasterxml.jackson.databind.annotation.JsonDeserialize;

import nl.knaw.dans.convert.jackson.StringByteSizeConverter;

class MyConfig {

    @JsonDeserialize(converter = StringByteSizeConverter.class)
    private long sizeInBytes;
}
```

