1. 請說明 Fixnum (整數) 和 Float (浮點數) 之間的差異  
**整數**，是序列{...，-3，-2，-1，0，1，2，3，...}中所有的數的統稱，包括負整數、零（0）與正整數。和自然數一樣，整數也是一個可數的無限集合。  
**浮點**（英語：floating point，縮寫為FP）是一種對於實數的近似值數值表現法，由一個有效數字（即尾數）加上冪數來表示，通常是乘以某個基數的整數次指數得到。  
以這種表示法表示的數值，稱為浮點數（floating-point number）。利用浮點進行運算，稱為浮點計算，這種運算通常伴隨著因為無法精確表示而進行的近似或捨入。  

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
str1和str2均為字串，第一個方法是用加號連結字串，第二個方法是用字串內插#{}來組合字串。

3. 請解釋 array 和 hash 的不同處  
**hash** 和**陣列**非常相近，唯一不同的是，陣列的索引值都是非負的整數，而 hash 的索引值可以是任何純量，通常我們將 hash 的索引值稱為 key，而將對應的對應的純量則稱為 value，所以整個 hash 可以看成是從 key 到 value 的一種關聯（Association）或映射（Mapping）。

4. 請用一行程式碼從 [1, "a string", 3.14, [1,2,3,4]] 這個陣列找出所有非字串的值

5. 請用一行程式碼把一個內容為整數 1 到 100 的陣列裡所有的值加上 2

6. 請寫出以下兩行程式碼迴傳的值，並解釋他們呼叫的方法差別為何：
  ```ruby
  [1, 2, 3, 3].uniq
  [1, 2, 3, 3].uniq!
  ```

7. 請列出兩種產出亂數的方法

8. 以下這段程式碼：
  ```ruby
  ((1 > 3)&&(true == true))||(!!!false)
  ```
  會執行出什麼結果？ 請試試不用 irb 算出結果  
true

9. 請問 binding.pry 是什麼？ 要如何使用它？
binding.pry 做的是 Runtime invocation。也就是可以在執行時攔截呼叫。這樣講你可能沒有感覺。

真正厲害的用途是： 例如搭配 Rails 使用，在程式碼裡面插入 binding.pry。打開 rails s

 class CourseController < ApplcationController
  def show
    @course = Course.find(params[:id])
    binding.pry
  end
當 browser 打開 http://localhost:3000/courses/30，pry 會自動攔下 request，跳出 console 供開發者 debug 。

From: /Users/xdite/Dropbox/projects/mentorhub/app/controllers/courses_controller.rb @ line 20 CoursesController#show:

    20: def show
    21:   @course = Course.find(params[:id])
 => 22:   binding.pry
    23: end
開發者可以在 console 直接就拉出 @course 這個 object 出來看

[1] pry(#<CoursesController>)> @course
=> #<Course id: 30, name: "voluptas", user_id: 1, course_topic_id: 2, plan: "Laboriosam labore soluta debitis excepturi consequa...", hourly_rate: 822, location: "Taipei", course_type: nil, created_at: "2012-08-12 09:41:21", updated_at: "2012-08-12 09:41:21", video_link: nil, video_link_html: nil>
也可以繼續追下去看裡面的東西

[2] pry(#<CoursesController>)> cd @course
[3] pry(#<Course>):1> plan
=> "Laboriosam labore soluta debitis excepturi consequatur et eos et et praesentium doloremque. qui debitis ab est rerum aut velit fuga ut nemo omnis eum praesentium voluptatem ut. eum fugit rerum fuga error architecto quod nesciunt assumenda in. dicta "
binding.pry 可以 Runtime 攔截呼叫物件，這讓開發者在寫一些複雜 Library 或者是 API 交涉資訊時，頓時就變得如虎添翼。因為每次在解決這類需求時，狀況都很像被綁黑布蒙著眼開發，最討厭的就是每次還要不斷的執行「印出」 debug，效率低落的驚人。


10. 下面的一段程式碼，請嘗試用其他方法把 if...else...end 簡化成一行

  ```ruby
  var = 5

  if var >= 5
  	return "var is greater than or equal to 5"
  else
  	return "var is less than 5"
  end
  ```

11. 請列出兩種不同的 hash 寫法
