# 常用字符串函数

## 字符串长度 len()

```go
func main(){
	var str string = "hello" //Golang 编码为UTF-8 汉字占用三个字节 字母数字只占用一个字节
	fmt.Printf("str lenth = %d\n", len(str))
}
```

## []rune()/[]byte()

参考文献：[rune 和 byte 的 区别](https://learnku.com/articles/23411/the-difference-between-rune-and-byte-of-go)

在写下这个的时候我翻阅了一些网上的文献 总结如下

```golang
func main(){
		var str = "女装山脉"
		fmt.Println([]rune(str)) // [22899 35013 23665 33033]
		fmt.Println([]byte(str)) // [229 165 179 232 163 133 229 177 177 232 132 137]
		//通过这里我们可以清楚的看出 这里每个汉字占用3个字节
		//Byte 表示一个字节 而 Rune用来表示4个字节
  
		r := []rune(str)
		for i := 0; i < len(); i++{
				printf("%c \n", r[i])
		}
}
```

## 整数转字符串 Atoi()

```go
func main(){
		n, err := strconv.Atoi("233")
		
		if err != nil {
				fmt.Println("Error ", err) //打印错误信息
		}else {
				fmt.Println("Atoi = ", n) //打印结果
	}
}
```

## 字符串转整数 Itoa()

```go
func main(){
		fmt.Println(strconv.Atoi(233)) //打印结果
}
```

## []byte 转字符串

```go
func main(){
		fmt.Printf("String = %v \n", string([]byte(97, 98, 99))) // a , b , c
}
```

## 进制转换 strconv.FormatInt()

```go
func main(){
		fmt.Println(" 8 的 2进制 = ", strconv.FormatInt(8, 2)) // strconv.FormatInt(数, 进制数)
}
```

## 是否存在子串 strings.Contains()

```go
func main(){
		fmt.Println(strings.Contains("Damedayo", "dayo"))
}
```

## 有几个子串 string.Count()

```go
func main(){
		fmt.Println(strings.Count("DamedamedameDaMe", "dame")) // 2 区分大小写
}
```

## 字符串比较 string.EqualFold()

```go
func main(){
		fmt.Println(string.EqualFold("bilibili", "BiLiBiLi")) // True
		//不区分大小写
}
```

## 子串第一次出现的位置 string.Index()

```go
func main(){
		fmt.Println(strings.Index("bilibili", "bi")) // 0
}
```

## 子串最后出现的位置 string.Lastindex()

```go
func main(){
		fmt.Println(strings.LastIndex("233bilibili", "li")) // 9
}
```

## 替换指定子串 strings.Replace()

```go
func main(){
		fmt.Println(strings.Replace("bilibili244", "244", "233", -1)) // 最后一个参数代表替换几次
}
```

## 分割字符串 strings.Split()

```go
func main(){
		strArr := strings.Split("bilibili,chenrui,233,🐎,❤️", ",")
		for i := 0; i < len(strArr); i++ {
				fmt.Println(strArr[i])
		}
}
```

## 大小写转换 strings.ToLower/Upper()

```go
func main(){
		fmt.Println(strings.ToLower("CHENRUI")) //chenrui
		fmt.Println(strings.ToUpper("chenrui")) //CHENRUI
}
```

## 去首尾空 strings.TrimSpace()

```go
func main(){
		fmt.Println(strings.TrimSpace(" Bilibili ")) //bilibili
}
```

## 去首尾指定字符 strings.Trim()

```go
func main(){
		fmt.Println(strings.Trim("?-?","?")) //-
}
```

## 去左边指定字符 strings.TrimLeft()

```go
func main(){
		fmt.Println(strings.TrimLeft("mumchenrui","mum")) // chenrui
}
```

## 去右边指定字符 strings.TrimRight()

```go
func main(){
		fmt.Println(strings.TrimRight("chenruimum","mum")) // chenrui
}
```

## 判断字符串以指定子串开头 strings.HasPrefix()

```go
func main(){
		fmt.Println(strings.HasPrefix("https://bilibili.com"),"https://") // true
}
```

## 判断字符串以指定子串结束 strings.HasSuffix()

```go
func main(){
		fmt.Println(strings.HasSuffix("bilibili.png",".png")) //true
}
```





