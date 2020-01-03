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
## if
```
func main() {
	answer := 6
	var guess int

	fmt.Print("Your guess? ")
	fmt.Scanf("%v", &guess)

	if answer == guess {
		fmt.Println("Bingo!")
	} else if answer > guess {
		fmt.Println("もう少し大きい数を。。")
	} else {
		fmt.Println("もう少し小さい数を。。")
	}
}
```
## 乱数
```
package main

import (
	"fmt"
	// rand関数の宣言
	"math/rand"
	// randのseed値生成のために宣言する
	"time"
)

func main() {
	// randのseed値を現在時刻を元に生成する（面倒臭いが。。
	rand.Seed(time.Now().UnixNano())
	// 1~10のランダムな数字を生成する
	answer := rand.Intn(10) + 1
	var guess int

	fmt.Print("Your guess? ")
	fmt.Scanf("%v", &guess)

	if answer == guess {
		fmt.Println("Bingo!")
	} else if answer > guess {
		fmt.Println("The answer is higher!")
	} else {
		fmt.Println("The anwer is lower!")
	}
	fmt.Printf("The answer is %v", answer)
}
```
## ループ処理
```
	// ループ
	for {
		fmt.Print("Your guess? ")
		fmt.Scanf("%v", &guess)
		
		if answer == guess {
			fmt.Println("Bingo!")
			// ループ抜け
			break
		} else if answer > guess {
			fmt.Println("The answer is higher!")
		} else {
			fmt.Println("The anwer is lower!")
		}
	}
```
## 数当てゲーム
```
package main

import (
	"fmt"
	"math/rand"
	"time"
)

func main() {
	rand.Seed(time.Now().UnixNano())
	answer := rand.Intn(10) + 1
	count := 0
	
	for {
		var guess int

		fmt.Print("Your guess? ")
		fmt.Scanf("%v", &guess)
		// 解答回数加算
		count++

		if answer == guess {
			fmt.Println("Bingo!")
			fmt.Printf("解答回数は %v でした", count)
			break
		} else if answer > guess {
			fmt.Println("The answer is higher!")
		} else {
			fmt.Println("The anwer is lower!")
		}
	}
}
```
