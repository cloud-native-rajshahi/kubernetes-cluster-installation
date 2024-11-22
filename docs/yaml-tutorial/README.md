# YAML Tutorial

YAML stands for "YAML Ain't Markup Language". However, initially it called as a "Yet Another Markup Language". 

[YAML™ (rhymes with “camel”)](https://yaml.org/spec/) is a human-friendly, cross language, Unicode based data serialization language designed around the common native data structures of agile programming languages. It is broadly useful for programming needs ranging from configuration files to Internet messaging to object persistence to data auditing. Together with the Unicode standard for characters, the YAML specification provides all the information necessary to understand YAML Version 1.2 and to creating programs that process YAML information.

Key Features of YAML:
- Human-readable: It's designed to be easy to read and write by humans, avoiding the complexity of formats like XML or JSON.
- Uses indentation: Structure in YAML is determined by indentation (similar to Python), making it visually intuitive.
- Data types: Supports common data types such as scalars (strings, integers, booleans), lists, and dictionaries (key-value pairs).
- No closing tags or braces: Unlike XML or JSON, YAML relies on indentation rather than closing tags or braces to define structure.


- Maps/Dictionaries (YAML calls it mapping)
- Arrays/Lists (YAML calls them sequences)
- Literals (Strings, numbers, boolean, etc.)


A YAML file relies on whitespace and indentation to indicate nesting. Notice the hierarchy and nesting is visible through a Python-like indentation style. It is critical to note that tab characters cannot be used for indentation in YAML files; only spaces can be used. The number of spaces used for indentation doesn’t matter as long as they are consistent.

## Example of a YAML Files


```yaml
# key: value [mapping]
company: spacelift
# key: value is an array [sequence]
domain:
 - devops
 - devsecops
tutorial:
  - yaml:
      name: "YAML Ain't Markup Language" #string [literal]
      type: awesome #string [literal]
      born: 2001 #number [literal]
  - json:
      name: JavaScript Object Notation #string [literal]
      type: great #string [literal]
      born: 2001 #number [literal]
  - xml:
      name: Extensible Markup Language #string [literal]
      type: good #string [literal]
      born: 1996 #number [literal]
author: omkarbirade
published: true

```



```yaml
apiVersion: kubeadm.k8s.io/v1beta4
kind: InitConfiguration
nodeRegistration:
  criSocket: unix:///var/run/crio/crio.sock
```


# References
- https://yaml.org/
- https://yaml.org/spec/
- https://yaml.org/spec/1.1/current.html
- https://github.com/yaml
- https://github.com/yaml/yamlscript
- https://spacelift.io/blog/yaml
- https://www.tutorialspoint.com/yaml/index.htm