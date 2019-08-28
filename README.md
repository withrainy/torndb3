# torndb3

torndb 兼容Py3

- zip 使用 itertools.zip_longest 替换

- CONVERSIONS 使用默认值


关于 CONVERSIONS:

```
A dictionary or mapping which controls how types are converted from MySQL to Python and vice versa.

If the key is a MySQL type (from FIELD_TYPE.*), then the value can be either:

a callable object which takes a string argument (the MySQL value),’ returning a Python value
a sequence of 2-tuples, where the first value is a combination of flags from MySQLdb.constants.FLAG, and the second value is a function as above. The sequence is tested until the flags on the field match those of the first value. If both values are None, then the default conversion is done. Presently this is only used to distinguish TEXT and BLOB columns.
If the key is a Python type or class, then the value is a callable Python object (usually a function) taking two arguments (value to convert, and the conversion dictionary) which converts values of this type to a SQL literal string value.

This is initialized with reasonable defaults for most types. When creating a Connection object, you can pass your own type converter dictionary as a keyword parameter. Otherwise, it uses a copy of MySQLdb.converters.conversions. Several non-standard types are returned as strings, which is how MySQL returns all columns. For more details, see the built-in module documentation.

```



