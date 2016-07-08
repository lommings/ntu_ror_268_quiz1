1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異

2. 今天有兩個字串：
  ```ruby 
  str1 = "Hallo Welt!" 
  str2 = " NTU Rails 261!"
  ```
請說明以下兩個印出字串的方式的不同處：
  ```ruby
  puts str1 + str2
  puts "#{str1}#{str2}"
  ```

3. 請解釋 array 和 hash 的不同處

4. 請寫一段 code 從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值

5. 請列出兩種產出亂數的方法

6. 請把 hoemowrk1 程式碼裡的裡面的使用者輸入兩個數字的方式和輸贏的判斷式改寫成 method

7. 以下這段程式碼：
  ```ruby
  ((1 > 3)&&(true == true))||(!!!false)
  ```
  會執行出什麼結果？ 請試試不用 irb 算出結果

8. 請問 binding.pry 是什麼？ 要如何使用它？

9. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行

  ```ruby
  var = 5

  if var >= 5
  	return "var is greater than or equal to 5"
  else
  	return "var is less than 5"
  end
  ```