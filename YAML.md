# YAML

We'll learn how to work with YAML file.

# Table of Contents

1. Introduction
2. Syntax
3. Properties/Data Types
4. YAML tools

# What is YAML?

Full form of YAML is **YAML Ain't Markup Language**, previously it was known as **Yet Another Markup Language**. It is a human-readable data serialization language to represent data. It is commonly used for configuration files, but could be used in many applications where data is being stored or transmitted.
The extension of YAML file is `.yml` or `.yaml`.

## What is a Markup Language?

A markup language is used provide child parent relationship to the data. For example, HTML is a markup language. In HTML, we use tags to define the relationship between the data. For example, `<h1>Heading</h1>` here `<h1>` is the tag and `Heading` is the data. In this case, `Heading` is the child of `<h1>` tag.

Shows how things are related to each other and layered.

YAML is a data-format used to exchange data between applications. It is similar to XML and JSON.Stores information regarding configuration, serialization, and persistence.

Only stores data, not code.

## What is data serialization?

Serialization is the process of converting an object into a stream of bytes to store the object or transmit it to memory, a database, or a file. Its main purpose is to save the state of an object in order to be able to recreate it when needed. The reverse process is called deserialization.

This helps to share data between different applications,like between Android App and Web App.

Object(data) ->Stream of bytes -> Store in memory, database or file -> stream -> convert back to object(data)

<b>Object -> Stream of bytes</b> is called serialization.
<b>Stream of bytes(file) -> Object</b> is called deserialization.

Object when goes into serialization, it is converted into stream of bytes. This stream of bytes can be stored in memory, database or file(YAML). When we need the object back, we can convert the stream of bytes back to object.

## Data serialization languages (representation of data in text format)

1. JSON
2. XML
3. YAML

## Why YAML? Why not JSON or XML?

YAML is a superset of JSON. It is easier to read and write than JSON. It is also easier to understand than XML. It is a human-readable data serialization language. It is commonly used for configuration files, but could be used in many applications where data is being stored or transmitted.

## Why is YAML not a markup language?

In HTML, you store documents.YAML is used to store data.

## What type of data can be stored in YAML?

Mainly used to store configuration data.
Used in logs, caches, configuration files, or any other place where humans need to look at the data and make sense of it.
Like in Kubernetes, we store configuration data in YAML file. This configuration data is used to create pods, services, deployments, etc.

## Benefits of YAML

1. Human-readable
2. Easy to understand
3. Easy to write
4. Easy to parse
5. Easy to generate
6. Supports comments
7. Supports multiple documents
8. Supports multiple data types
9. Supports Unicode
10. Supports serialization and deserialization
11. Supports cross-language implementations
12. Supports one-line comments
13. Supports inline comments
14. Supports multi-line comments
15. Supports anchors and references
16. Supports complex data structures
17. Supports rich data types
18. Supports user-defined data types
19. Supports self-referencing data types
20. Supports recursive data types
21. Easily convert to JSON and vice versa

# Syntax

It is very necessary to keep in mind that indentation is very important in YAML. It is used to define the relationship between the data. It is similar to the indentation in Python.

YAML is a case-sensitive language. It means that the data is case-sensitive. For example, `name` and `Name` are two different things in YAML.

You can check the syntax of YAML file using parsers like [YAML Lint](http://www.yamllint.com/).

## Comments

Comments are used to explain the code. It is used to make the code more readable. It is not executed by the compiler. It is represented by a hash(#) symbol.

```yaml
# This is a comment
```

<b>Example:</b>

```yaml
# This is a comment
name: John
```

## Multiple Documents

It is interesting to note that YAML supports multiple documents in a single file(object). It is represented by three hyphens(---) at the beginning of the document and three dots(...) at the end of the document.

```yaml
---
document1
---
document2
---
document3
...
```

## Variables

Variables are used to store data. It is represented by a colon(:) between the key and value. Key is the name of the variable and value is the data stored in the variable. The key and value are separated by a space.

Variables should always be present. If the variable is not present, then it will throw an error.

```yaml
key: value
```

## Data types

1. Scalar
2. Sequence
3. Mapping
4. Pairs
5. Set
6. Dictionary

### Mapping(Dictionary/Hash Map)

Mapping is a collection of key-value pairs. It is similar to a dictionary in Python. It is represented by a colon(:) between the key and value. The key and value are separated by a space.
Data type is !!map.

Types of mapping:

1. Nested mapping: A mapping inside a mapping is called a nested mapping.
2. Explicit mapping: A mapping with !!map is called an explicit mapping.
3. Implicit mapping: A mapping without !!map is called an implicit mapping.

```yaml
key: value
```

<b>Example:</b>

```yaml
name: John
age: 30
```

### Sequence(List)

List is a collection of items. It is similar to a list in Python. It is represented by a hyphen(-) before the item. The items are separated by a space.

The data type of the items in the list can be different. It can be a string, integer, float, Boolean, etc.
Denoted by a hyphen(-) before the item.
Data type is !!seq.

1. Sparse seq: A seq with empty items is called a sparse list.
2. Explicit seq: A seq with !!seq is called an explicit list.
3. Implicit seq: A seq without !!seq is called an implicit list.
4. Nested seq: A seq inside a seq is called a nested list.

<b>Examples:</b>

```yaml
# Sparse seq
- item1
- item2
- item3
-
- item5
# Explicit seq
!!seq [item1, item2, item3]
# Implicit seq
[item1, item2, item3]
# Nested seq
- item1
- item2
  - item3
  - item4
```

```yaml
- item1
- item2
```

<b>Example:</b>

```yaml
- John
- 30
```

### Scalar(Single value/Variable/Constant)

Scalar is a single value. It is similar to a variable in Python. It is represented by a colon(:) between the key and value. The key and value are separated by a space.

Scalar is a simple data type. In YAML, scalar means a simple value for a key. The value of the scalar can be integer, float, Boolean, and string. Scalar data types are classified into two data types:

1. Numeric Data type : Integer, Float and Boolean
2. String (Text) Data type : String
3. Null Data type : Null
4. Date and Time Data type : Timestamp

```yaml
key: value
```

<b>Example:</b>

```yaml
name: John
age: 30
```

#### Numeric Data type

1. Integer
2. Float
3. Boolean

##### Integer

Integer is a whole number. It is similar to an integer in Python. It is represented by a colon(:) between the key and value. The key and value are separated by a space.

```yaml
key: 568
```

##### Float

Float is a decimal number. It is similar to a float in Python. It is represented by a colon(:) between the key and value. The key and value are separated by a space.

```yaml
key: 56.8
marks: !!float 56.8
infinity: !!float .inf
not a number: !!float .nan
```

##### Boolean

Boolean is a true or false value or yes/no,n/f,N/F. It is similar to a Boolean in Python. It is represented by a colon(:) between the key and value. The key and value are separated by a space.

```yaml
key: true
```

#### String

String is a collection of characters. It is similar to a string in Python. It is represented by a colon(:) between the key and value. The key and value are separated by a space.

There are 3 ways to represent a string in YAML:

1. Single Quoted
2. Double Quoted
3. Literal Style

##### Writing in multiple lines

We can write a string in multiple lines. It is represented by a pipe(|) symbol. The pipe symbol is written after the colon(:) and the string is written in the next line.

```yaml
key: |
  value
```

##### Single line in multiple lines

We can write a single line in multiple lines. It is represented by a greater than(>) symbol. The greater than symbol is written after the colon(:) and the string is written in the next line.

```yaml
key: >
  value
```

### Pairs

Keys may have duplcate values. Data type is !!pairs.
Internally, it will be stored as hash table containing arrays.

```yaml
pairs:
  - key: value
  - key: value
```

### Set

Keys may not have duplcate values. Data type is !!set.

```yaml
set:
  key:
  Anu:
```

### Dictionary

Keys' value are sequence of key-value pairs. Data type is !!omap.

```yaml
omap: !!omap
  - Anu:
      name: Anu
      age: 30
  - John:
      name: John
      age: 30
```

## Data Structures

1. Block Style
2. Inline Style

### Block Style (Complex data structures)

Block style is used to represent complex data structures. It is represented by a colon(:) after the key. The key and value are separated by a space. The value is represented by a hyphen(-) before the item. The items are separated by a space.

```yaml
key:
  - item1
  - item2
```

<b>Example:</b>

```yaml
name:
  - John
  - Doe
```

### Inline Style (Complex data structures)

Inline style is used to represent complex data structures. It is represented by a colon(:) after the key. The key and value are separated by a space. The value is represented by a hyphen(-) before the item. The items are separated by a comma(,).

```yaml
key: [item1, item2]
```

<b>Example:</b>

```yaml
name: [John, Doe]
# Key-Value pair
{mark: 50, age: 30}
```

## YAML to JSON

We can convert YAML to JSON and vice versa. It is very easy to convert YAML to JSON. We can use [YAML to JSON](https://www.json2yaml.com/) to convert YAML to JSON.

## Specify data types

If you want to specify type in data types use `!!` and then specify the data type.

```yaml
key: !!data_type value
```

<b>Example:</b>

```yaml
name: !!str John
age: !!int 30
positiveNumber: !!float 56.8
negativeNumber: !!float -56.8
binary: !!bool true
octal: !!int 0o137
hexadecimal: !!int 0x7f
sexagesimal: !!int 1:30
date: !!timestamp 2021-06-21
null: !!null null
commaValue: !!int +1_000_000
exponentialNotation: !!float 12e+2
```

## Anchors and References

Anchors and references are used to reuse the data. It is represented by an ampersand(&) before the anchor name and an asterisk(\*) before the reference name.

<b>Example:</b>

```yaml
# Anchors
name: &name John
age: 30
# References
name: *name
age: 30
```

### Anchors

What is the property you want to use?

```yaml
likings: &base # base is the anchor name
  - apple
  - orange
  - banana
person:
  name: John
  <<: *base # << is used to merge the data
# Override the data
person2:
  name: Johnny
  likings:
    - apple
    - orange
    - banana
    - mango
```

### References

Reference is used to reuse the data. It is represented by an asterisk(\*) before the reference name.

```yaml
name: &name John
age: 30
person:
  name: *name
  age: 30
```
