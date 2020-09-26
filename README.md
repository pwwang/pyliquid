# liquidpy
A port of [liquid][1] template engine for python

[![Pypi][2]][9] [![Github][3]][10] [![PythonVers][4]][9] [![ReadTheDocs building][13]][8] [![Travis building][5]][11] [![Codacy][6]][12] [![Codacy coverage][7]][12]

This is compatible with [standard Liquid][1] template engine. Variations, such as Shopify and Jekyll are not fully supported yet.

## Install
```shell
pip install liquidpy
```

## Baisic usage
```python
from liquid import Liquid
liq = Liquid('{{a}}')
ret = liq.render(a=1)
# ret == '1'

# with environments pre-loaded
liq = Liquid('{{a}}', a=1)
ret = liq.render()
# ret == '1'

# With debug on:
liq = Liquid('{{a}}', liquid_config={'debug': True})
```

## Python mode

We also support a python mode template engine, which acts more pythonic and powerful.
```python
from liquid import Liquid
# standard liquid doesn't support this
liq = Liquid('{{a + 1}}', {'mode': 'python'})
ret = liq.render(a=1)
# ret == '2'
```

Both modes can accept a path, a file-like object or a stream for the template:
```python
Liquid('/path/to/template')
# or
with open('/path/to/template') as f:
    Liquid(f)
```

## Full Documentation
- Liquid's [documentation][1]
- Liquidpy's [documentation][14]

[1]: https://shopify.github.io/liquid/
[2]: https://img.shields.io/pypi/v/liquidpy.svg?style=flat-square
[3]: https://img.shields.io/github/tag/pwwang/liquidpy.svg?style=flat-square
[4]: https://img.shields.io/pypi/pyversions/liquidpy.svg?style=flat-square
[5]: https://img.shields.io/travis/pwwang/liquidpy.svg?style=flat-square
[6]: https://img.shields.io/codacy/grade/aed04c099cbe42dabda2b42bae557fa4?style=flat-square
[7]: https://img.shields.io/codacy/coverage/aed04c099cbe42dabda2b42bae557fa4?style=flat-square
[8]: https://liquidpy.readthedocs.io/en/latest/
[9]: https://pypi.org/project/liquidpy/
[10]: https://github.com/pwwang/liquidpy
[11]: https://travis-ci.org/pwwang/liquidpy
[12]: https://app.codacy.com/manual/pwwang/liquidpy/dashboard
[13]: https://img.shields.io/readthedocs/liquidpy?style=flat-square
[14]: https://pwwang.github.io/liquidpy/
