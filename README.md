# study_go
# 基本文法
## 簡単な全体像
```
// プログラムの単位的なもの
package main

// 文字列を表示させるパッケージ的なもの
import (
	"fmt"
)

// 関数
func main(){
  // 変数の宣言
	// var name string = "togashi"
	name := "togashi"
	fmt.Println("hello!")	
}

```
## printlnとprintf
```
func main() {
	name := "taguchi"
	// Printfは変数を埋め込めるが、改行コードを自分で入れる必要がある
	fmt.Printf("hello %v\n", name)
	fmt.Printf("hello %v again!", name)
}
```
## Scanf
入力待ちをする
```
func main() {
	var guess int
	
	fmt.Println("入力するでごんす")
	// 入力を受け付ける関数（受け付けとる変数, 保存先の変数）
	fmt.Scanf("%v", &guess)
	fmt.Printf("入力した値は %v でごんす", guess)
}
```

