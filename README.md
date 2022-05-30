# Halstead Metric and Cyclomatic Complexity for java

calculates Halstead Metric and Cyclomatic Complexity for a given java file

## installation

```bash
py -m venv venv
venv/Scripts/python -m pip install -r requirements.txt
```

## args

```bash
(venv) $ py -m halstead_cyclomatic -h
```

```text
usage: __main__.py [-h] JAVA_FILE

outputs Halstead metrics and cyclomatic complexity for a given java file

positional arguments:
  JAVA_FILE   path to the java file

options:
  -h, --help  show this help message and exit
```

## examples

java examples can be found in the [examples](examples/) folder

### 3.java

#### Java

```java
class Test2 {
    public static void main(String[] args) {
        int[][] a = { { 00, 01 }, { 10, 11 } };
        int i = 99;
        try {
            a[val()][i = 1]++;
        } catch (Exception e) {
            System.out.println(e + ", i=" + i);
        }
    }
    static int val() throws Exception {
        throw new Exception("unimplemented");
    }
}
```

#### Output

```bash
(venv) $ py -m halstead_cyclomatic examples/3.java
```

```text
Operators:
        class:  1
        {:      8
        public: 1
        static: 2
        void:   1
        (:      6
        [:      5
        ]:      5
        ):      6
        int:    3
        =:      3
        ,:      3
        }:      8
        ;:      5
        try:    1
        ++:     1
        catch:  1
        .:      2
        +:      2
        throws: 1
        throw:  1
        new:    1
Operands:
        Test2:                  1
        main:                   1
        String:                 1
        args:                   1
        a:                      2
        00:                     1
        01:                     1
        10:                     1
        11:                     1
        i:                      3
        99:                     1
        val:                    2
        1:                      1
        Exception:                      3
        e:                      2
        System:                 1
        out:                    1
        println:                        1
        ", i=":                 1
        "unimplemented":                        1

------------------------------------------------------------------------------------------------------------------------------------------------------

n1:     22
n2:     20
N1:     67
N2:     27

------------------------------------------------------------------------------------------------------------------------------------------------------

Halstead Complexity:

        Program vocabulary:                                             42
        Program length:                                         94
        Estimated length:                                               184.55
        Purity ratio:                                           1.96
        Volume:                                         995.13
        Difficulty:                                             14.85
        Program effort:                                         14777.69
        Time required to program:                                               820.98
        Number of delivered bugs:                                               0.33

------------------------------------------------------------------------------------------------------------------------------------------------------

Cyclomatic complexity: 1
```
