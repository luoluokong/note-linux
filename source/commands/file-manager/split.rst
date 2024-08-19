==========
split 命令
==========

分割大文件，默认每1000行分割一次。

-----------

----
语法
----
::

    split [-option param] <待处理文件> [输出的文件名前缀]

**选项** ::

    -b: 每个输出文件的大小(byte)；
    -C: 每个输出文件，单行最大的 byte 数(尽量保持每一行的完整性)；
    -l: 每个输出文件的行数；
    -a: 输出文件的后缀长度(2)；
    -d: 使用数字作为后缀(选项放前面)；
    -n: 分割为 n 个文件；

----
实例
----

1. 按10MB拆分：

.. code-block:: console
    
    $ split -b 10M data data-
    $ ls
    $ data data-aa data-ab ... data-aj

2. 按5k行拆分，后缀使用数字；

.. code-block:: console

    $ split -d -l 5000 data data-
    $ ls
    $ data data-01 data-02 ...

3. 拆分为5个文件；

.. code-block:: console

    $ split -n 5 data data-
    $ ls
    $ data data-aa data-ab ... data-ae
