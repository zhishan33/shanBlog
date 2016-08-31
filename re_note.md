## 正则表达式

- **匹配重复数字**
- **匹配连续数字**

### 匹配重复数字

```
<script type="text/javascript">
var reText = "22222",
	reText1 = "aaaa";
	/^(\w)\1{4,13}$/.test(reText) //true
	/^(\w)\1{4,13}$/.test(reText1) //true
			
</script>
```

### 匹配字符串中的重复字母或数字

```
<script type="text/javascript">
var reText = "22222",
	reText1 = "aaaa";
	/^(\w)*(\d)\2{2}(\w)*$/.test(reText) //true 匹配重复大于3位及以上
	/^(\w)*(a-Z)\2{2}(\w)*$/.test(reText1) //true
			
</script>
```

### 匹配连续数字

```
<script type="text/javascript">
var reText = "12345",
	reText1 = "876543";
	/^(?:0(?=1)|1(?=2)|2(?=3)|3(?=4)|4(?=5)|5(?=6)|6(?=7)|7(?=8)|8(?=9)|9(?=0))+\d$/.test(reText) //true
	/^(?:9(?=8)|8(?=7)|7(?=6)|6(?=5)|5(?=4)|4(?=3)|3(?=2)|2(?=1)|1(?=0)|0(?=0))+\d$/.test(reText1) //true
			
</script>
```