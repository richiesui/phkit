
![phkit](phkit.png "phkit")

## phkit
phoneme toolkit: 音素相关的文本处理工具箱。

### 安装

```
pip install -U phkit
```

### v0.2.1
- 增加中文的text_to_sequence方法，可替换英文版本应对中文环境。
- 兼容v0.1.0（含）之前版本需要在python3.7（含）版本以上，否则请改为从phkit.chinese导入模块。

### v0.2.0
- 增加文本转拼音的模块，依赖python-pinyin，jieba，phrase-pinyin-data模块。
- 中文的音素方案移动到chinese模块。

### v0.1.0
- 增加英文版本的音素方案，包括英文字母和英文音素。
- 增加简单的数字转中文的方法。

todo:
文本正则化处理
数字读法
字符读法
常见规则读法


文本转拼音
pypinyin
国标和alnum转换

anything转音素
字符
英文
汉字
OOV

进阶:
分词
命名实体识别
依存句法分析

### 版本
v0.2.1

## pinyinkit
文本转拼音的模块，依赖python-pinyin，jieba，phrase-pinyin-data模块。

## chinese
适用于中文、英文和中英混合的音素，其中汉字拼音采用清华大学的音素，英文字符分字母和英文。

中文音素简介：

声母：
aa b c ch d ee f g h ii j k l m n oo p q r s sh t uu vv x z zh

韵母：
a ai an ang ao e ei en eng er i ia ian iang iao ie in ing iong iu ix iy iz o ong ou u ua uai uan uang ueng ui un uo v van ve vn ng uong

声调：
1 2 3 4 5

字母：
Aa Bb Cc Dd Ee Ff Gg Hh Ii Jj Kk Ll Mm Nn Oo Pp Qq Rr Ss Tt Uu Vv Ww Xx Yy Zz

英文：
A B C D E F G H I J K L M N O P Q R S T U V W X Y Z

标点：
! ? . , ; : " # ( )
注：!=!！|?=?？|.=.。|,=,，、|;=;；|:=:：|"="“|#= 　	|(=(（[［{｛【<《|)=)）]］}｝】>》

预留：
w y 0 6 7 8 9

其他：
_ ~  - *

### symbol
音素标记。
中文音素，简单英文音素，简单中文音素。

### sequence
转为序列的方法，文本转为音素列表，文本转为ID列表。

拼音变调，拼音转音素。

### pinyin
转为拼音的方法，汉字转拼音，分离声调。

拼音为字母+数字形式，例如pin1。

### phoneme
音素映射表。

不带声调拼音转为音素，声调转音素，英文字母转音素，标点转音素。

### number
数字读法。

按数值大小读，一个一个数字读。

### convert
文本转换。

全角半角转换，简体繁体转换。

## english

from https://github.com/keithito/tacotron "
Cleaners are transformations that run over the input text at both training and eval time.

Cleaners can be selected by passing a comma-delimited list of cleaner names as the "cleaners"
hyperparameter. Some cleaners are English-specific. You'll typically want to use:
  1. "english_cleaners" for English text
  2. "transliteration_cleaners" for non-English text that can be transliterated to ASCII using
     the Unidecode library (https://pypi.python.org/pypi/Unidecode)
  3. "basic_cleaners" if you do not want to transliterate (in this case, you should also update
     the symbols in symbols.py to match your data).
