<p align="center">
  <img src="https://github.com/UlionTse/translators/blob/master/docs/translators_logo.png" width="500"/>
</p>
<p align="center">
  <a href="https://pypi.org/project/translators"><img alt="PyPI - Version" src="https://img.shields.io/pypi/v/translators.svg"></a>
  <a href="https://pypi.org/project/translators"><img alt="PyPI - License" src="https://img.shields.io/pypi/l/translators.svg"></a>
  <a href="https://pypi.org/project/translators"><img alt="PyPI - Python" src="https://img.shields.io/pypi/pyversions/translators.svg"></a>
  <a href="https://pypi.org/project/translators"><img alt="PyPI - Status" src="https://img.shields.io/pypi/status/translators.svg"></a>
  <a href="https://pypi.org/project/translators"><img alt="PyPI - Wheel" src="https://img.shields.io/badge/wheel-yes-brightgreen.svg"></a>
  <a href="https://pypi.org/project/translators"><img alt="Downloads" src="https://pepy.tech/badge/translators"></a>
</p>

* * *

**Translators** is a library which aims to bring **free, multiple, enjoyable** translation to individuals and students in Python. It based on the translation interface of Google, Yandex, Microsoft(Bing), Baidu, Alibaba, Tencent, NetEase(Youdao), Sogou, Deepl, etc.   

The old version is called **translate-api** ![downloads](https://pepy.tech/badge/translate-api), and it is updated synchronously now.


- [Installation](#installation)
  - [From PyPI](#from-PyPI)
  - [From Source](#from-source)
- [Getting Started](#getting-started)
    - [Import library](#Import-library)
    - [Language](#Language)
    - [Professional Field](#Professional-Field)
    - [Property](#Property)
    - [Requests](#Requests)
    - [Host](#Host)
    - [Detail Result](#Detail-Result)
    - [Help](#Help)
- [Issues]()
    - [Linux Runtime Environment](#linux-runtime-environment)
    - [Supported Country and Region Service](#supported-country-and-region-service)
    - [HTTPError 4xx](#httperror-4xx)
- [More About Translators](#more-about-translators)
    - [Features](#features)
    - [Support Language](#support-language)
    - [About Chinese Language](#about-Chinese-language)
- [License](#License)



## Installation

### From PyPI

```shell
# Windows, Mac, Linux
pip install translators --upgrade

# Linux javascript runtime environment:
sudo yum -y install nodejs
```

### From Source

```bash
git clone https://github.com/UlionTse/translators.git
cd translators
python setup.py install
```

## Getting Started

```python
import translators as ts

wyw_text = '季姬寂，集鸡，鸡即棘鸡。棘鸡饥叽，季姬及箕稷济鸡。'
chs_text = '季姬感到寂寞，罗集了一些鸡来养，鸡是那种出自荆棘丛中的野鸡。野鸡饿了唧唧叫，季姬就拿竹箕中的谷物喂鸡。'

# input languages
print(ts.deepl(wyw_text)) # default: from_language='auto', to_language='en'

## output language_map
print(ts._deepl.language_map)

# professional field
print(ts.alibaba(wyw_text, professional_field='general')) # ("general","message","offer")
print(ts.baidu(wyw_text, professional_field='common')) # ('common','medicine','electronics','mechanics')

# property
rs = [ts.tencent(x) for x in [wyw_text, chs_text]]
print(ts._tencent.query_count)
print(dir(ts._tencent))

# requests
print(ts.youdao(wyw_text, sleep_seconds=5, proxies={}, use_cache=True))

# host service
print(ts.google(wyw_text, if_use_cn_host=True))
print(ts.bing(wyw_text, if_use_cn_host=False))

# detail result
print(ts.sogou(wyw_text, is_detail_result=True)
      
# help
help(ts.deepl)
```

## Issues

### Linux Runtime Environment

1. To support javascript runtime environment, you should `sudo yum -y install nodejs `.
2. PS, `ts.baidu()` does not work on Linux without desktop.

### Supported Country and Region Service

1. If you have requests error, please check whether this service is provided in your country or region.
2. Check the website about `eg: help(ts.google)`.

### HTTPError 4xx

1. Please check whether you made high frequency requests.
2. Please check whether this service is provided in your country or region.
3. Detail to solve [HTTPError](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status) itself.
4. Please [issues me](https://github.com/UlionTse/translators/issues), thanks.

## More About Translators

### Features

| Translator | Supported Language Count | Advantage                                                  |
| ---------- | ------------------------ | ---------------------------------------------------------- |
| Google     | 108                      | support the most languages in the world                    |
| Yandex     | 99                       | support more languages in the world, support word to emoji |
| Bing       | 77                       | support more languages in the world                        |
| Sogou      | 61                       | support more languages in the world                        |
| Baidu      | 28                       | support more languages, support professional field         |
| Tencent    | 17                       | support more languages                                     |
| Youdao     | 14                       | support more languages                                     |
| Alibaba    | 12                       | support more languages, support professional field         |
| Deepl      | 11                       | high quality to translate but response slowly              |



### Support Language



| Language             | Language of Translator | Google | Yandex | Bing               | Baidu  | Alibaba | Tencent | Youdao | Sogou              | Deepl |
| -------------------- | ---------------------- | ------ | ------ | ------------------ | ------ | ------- | ------- | ------ | ------------------ | ----- |
| english              | en                     | Y      | Y      | Y                  | Y      | Y       | Y       | Y      | Y                  | Y     |
| chinese              | zh                     | Y      | Y      | Y                  | Y      | Y       | Y       | Y      | Y                  | Y     |
| arabic               | ar                     | Y      | Y      | Y                  | Y(ara) | Y       | Y       | Y      | Y                  |       |
| russian              | ru                     | Y      | Y      | Y                  | Y      | Y       | Y       | Y      | Y                  | Y     |
| french               | fr                     | Y      | Y      | Y                  | Y(fra) | Y       | Y       | Y      | Y                  | Y     |
| german               | de                     | Y      | Y      | Y                  | Y      |         | Y       | Y      | Y                  | Y     |
| spanish              | es                     | Y      | Y      | Y                  | Y(spa) | Y       | Y       | Y      | Y                  | Y     |
| portuguese           | pt                     | Y      | Y      | Y(pt/pt-pt)        | Y      | Y       | Y       | Y      | Y                  | Y     |
| italian              | it                     | Y      | Y      | Y                  | Y      | Y       | Y       | Y      | Y                  | Y     |
| japanese             | ja                     | Y      | Y      | Y                  | Y(jp)  |         | Y       | Y      | Y                  | Y     |
| korean               | ko                     | Y      | Y      | Y                  | Y(kor) |         | Y       | Y      | Y                  |       |
| greek                | el                     | Y      | Y      | Y                  | Y      |         |         |        | Y                  |       |
| dutch                | nl                     | Y      | Y      | Y                  | Y      |         |         | Y      | Y                  | Y     |
| hindi                | hi                     | Y      | Y      | Y                  |        |         | Y       |        | Y                  |       |
| turkish              | tr                     | Y      | Y      | Y                  |        | Y       | Y       |        | Y                  |       |
| malay                | ms                     | Y      | Y      | Y                  |        |         | Y       |        | Y                  |       |
| thai                 | th                     | Y      | Y      | Y                  | Y      | Y       | Y       |        | Y                  |       |
| vietnamese           | vi                     | Y      | Y      | Y                  | Y(vie) | Y       | Y       | Y      | Y                  |       |
| indonesian           | id                     | Y      | Y      | Y                  |        | Y       | Y       | Y      | Y                  |       |
| hebrew               | he                     | Y(iw)  | Y      | Y                  |        |         |         |        | Y                  |       |
| polish               | pl                     | Y      | Y      | Y                  | Y      |         |         |        | Y                  | Y     |
| mongolian            | mn                     | Y      | Y      |                    |        |         |         |        |                    |       |
| czech                | cs                     | Y      | Y      | Y                  | Y      |         |         |        | Y                  |       |
| hungarian            | hu                     | Y      | Y      | Y                  | Y      |         |         |        | Y                  |       |
| estonian             | et                     | Y      | Y      | Y                  | Y(est) |         |         |        | Y                  |       |
| bulgarian            | bg                     | Y      | Y      | Y                  | Y(bul) |         |         |        | Y                  |       |
| danish               | da                     | Y      | Y      | Y                  | Y(dan) |         |         |        | Y                  |       |
| finnish              | fi                     | Y      | Y      | Y                  | Y(fin) |         |         |        | Y                  |       |
| romanian             | ro                     | Y      | Y      | Y                  | Y(rom) |         |         |        | Y                  |       |
| swedish              | sv                     | Y      | Y      | Y                  | Y(swe) |         |         |        | Y                  |       |
| slovenian            | sl                     | Y      | Y      | Y                  | Y(slo) |         |         |        | Y                  |       |
| persian/farsi        | fa                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| bosnian              | bs                     | Y      | Y      | Y(bs-Latn)         |        |         |         |        | Y(bs-Latn)         |       |
| serbian              | sr                     | Y      | Y      | Y(sr-Latn/sr-Cyrl) |        |         |         |        | Y(sr-Latn/sr-Cyrl) |       |
| fijian               | fj                     |        |        | Y                  |        |         |         |        | Y                  |       |
| filipino             | tl                     | Y      | Y      | Y(fil)             |        |         |         |        | Y(fil)             |       |
| haitiancreole        | ht                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| catalan              | ca                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| croatian             | hr                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| latvian              | lv                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| lithuanian           | lt                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| urdu                 | ur                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| ukrainian            | uk                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| welsh                | cy                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| tahiti               | ty                     |        |        | Y                  |        |         |         |        | Y                  |       |
| tongan               | to                     |        |        | Y                  |        |         |         |        | Y                  |       |
| swahili              | sw                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| samoan               | sm                     | Y      |        | Y                  |        |         |         |        | Y                  |       |
| slovak               | sk                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| afrikaans            | af                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| norwegian            | no                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| bengali              | bn                     | Y      | Y      | Y(bn-BD)           |        |         |         |        | Y                  |       |
| malagasy             | mg                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| maltese              | mt                     | Y      | Y      | Y                  |        |         |         |        | Y                  |       |
| queretaro otomi      | otq                    |        |        | Y                  |        |         |         |        | Y                  |       |
| klingon/tlhingan hol | tlh                    |        |        | Y                  |        |         |         |        | Y                  |       |
| gujarati             | gu                     | Y      | Y      | Y                  |        |         |         |        |                    |       |
| tamil                | ta                     | Y      | Y      | Y                  |        |         |         |        |                    |       |
| telugu               | te                     | Y      | Y      | Y                  |        |         |         |        |                    |       |
| punjabi              | pa                     | Y      | Y      | Y                  |        |         |         |        |                    |       |
| amharic              | am                     | Y      | Y      |                    |        |         |         |        |                    |       |
| azerbaijani          | az                     | Y      | Y      |                    |        |         |         |        |                    |       |
| bashkir              | ba                     |        | Y      |                    |        |         |         |        |                    |       |
| belarusian           | be                     | Y      | Y      |                    |        |         |         |        |                    |       |
| cebuano              | ceb                    | Y      | Y      |                    |        |         |         |        |                    |       |
| chuvash              | cv                     |        | Y      |                    |        |         |         |        |                    |       |
| esperanto            | eo                     | Y      | Y      |                    |        |         |         |        |                    |       |
| basque               | eu                     | Y      | Y      |                    |        |         |         |        |                    |       |
| irish                | ga                     | Y      | Y      | Y                  |        |         |         |        |                    |       |
| emoji                | emj                    |        | Y      |                    |        |         |         |        |                    |       |
| ...                  | ...                    |        |        |                    |        |         |         |        |                    |       |

More supported language, eg:

```python
print(ts._google.language_map)
```



### About Chinese Language

| Language        | Language of Translator | Google   | Yandex | Bing       | Baidu  | Alibaba  | Tencent | Youdao | Sogou | Deepl |
| --------------- | ---------------------- | -------- | ------ | ---------- | ------ | -------- | ------- | ------ | ----- | ----- |
| chinese(简体)   | zh-CHS                 | Y(zh-CN) | Y(zh)  | Y(zh-Hans) | Y(zh)  | Y(zh)    | Y(zh)   | Y      | Y     | Y(zh) |
| chinese(繁体)   | zh-CHT                 | Y(zh-TW) |        | Y(zh-Hant) | Y(cht) | Y(zh-TW) |         |        | Y     |       |
| chinese(文言文) | wyw                    |          |        |            | Y      |          |         |        |       |       |
| chinese(粤语)   | yue                    |          |        | Y          | Y      |          |         |        | Y     |       |
| chinese(白苗文) | mww                    |          |        | Y          |        |          |         |        | Y     |       |



License

- Prohibition of commercial use !

  This library is designed to help students and individuals with translation services. For commercial use, please purchase API services from translation suppliers.

- Don't make high frequency requests !

  Enterprises provide free services, we should keep grateful, but not cause trouble.

[click the detail license.](https://github.com/uliontse/translators/blob/master/LICENSE)

