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

## Data types

1. Scalar
2. Sequence
3. Mapping

### Mapping(Dictionary/Hash Map)

Mapping is a collection of key-value pairs. It is similar to a dictionary in Python. It is represented by a colon(:) between the key and value. The key and value are separated by a space.

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

```yaml
key: value
```

<b>Example:</b>

```yaml
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
```
