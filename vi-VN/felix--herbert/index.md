---
title: Felix và Herbert
level: Level 1
materials: "Felix-and-Herbert.sb2"
notes: "notes for club leaders.md"
layout: project
---

# Giới thiệu { .intro}
Chúng ta sẽ cùng làm một trò chơi đuổi bắt với __mèo Felix__ và chuột __Herbert__. You control Herbert with the mouse and try to avoid getting caught by Felix. The longer you avoid him the more points you score, but don’t get caught because your score will go down!

![screenshot](felixherbert_screenshot.png)

# BƯỚC 1: Felix di chuyển theo con trỏ chuột { .activity}

## Bảng liệt kê các hoạt động cần kiểm tra { .check}

+ **Start a new program.**

+ Click vào **stage** bên cạnh hình sprit và chuyển sang thẻ `Backdrops` {.blocklightgrey}, sau đó click vào nút `Choose Backdrop from library` {.blocklightgrey} và chọn backdrop indoors/hall. Xóa backdrop trống ban đầu.  

+ Click vào hình sprit, và sau đó click vào nút `i` kéo đến phía trái của hình sprit. Đổi tên của hình sprite thành **Felix**.
+ Đảm bảo Felix chỉ di chuyển trái - phải khi click vào nút này: 
+ **Create this script**:

```blocks
				when FLAG clicked
				forever
					point towards [mouse-pointer v]
					move (10) steps
					next costume
					play drum (3 v) for (0.3) beats
				end
```

##Chạy thử chương trình{ .flag}

**Click the green flag.**

Felix có di chuyển theo đúng hướng con trỏ chuột không? Khi di chuyển, chú mèo có trông giống như đang đi bộ không? Tốc độ di chuyển đã ổn chưa? 

##Lưu lại dự án của bạn { .save}


#**Step 2:**   Felix đuổi theo Herbert {.activity}

*Next, we want Felix to chase Herbert the mouse, rather than the mouse pointer.*

##Bảng liệt kê các hoạt động cần kiểm tra { .check}

+ Tạo 1 hình sprit khác sử dụng nút `choose sprite from library` {.blockgrey} và chọn **animals/mouse1**.
+ Đổi tên của hình sprit thành **Herbert**.
+ Chuyển sang thẻ __Costumes__, sau đó click vào trang phục ở Paint Editor. 1 hộp sẽ hiện ra xung quanh trang phục. Kéo 1 góc hộp để làm Herbert nhỏ hơn Felix.  
+ Đảm bảo Herbert chỉ di chuyển trái - phải.
+ **Give Herbert this script:**

```blocks
  when FLAG clicked
    forever
      go to [mouse-pointer v]
      point towards [Felix v]
    end
```

##Chạy thử chương trình { .flag}

**Click the green flag.**

Herbert có di chuyển theo con trỏ chuột không? Felix có đuổi theo Herbert không? 

##Lưu lại dự án của bạn { .save}


#**Step 3:**   Felix nói khi bắt được Herbert {.activity}

**We want Felix to know when he’s caught Herbert, and tell us.** (Chúng tôi muốn Felix biết khi bắt được Herbert, vad nói cho chúng tôi)

##Bảng liệt kê các hoạt động cần kiểm tra { .check}

+ **Change Felix’s script to be this:** (Thay đổi tập lệnh của Felix thành:)

```blocks
  when FLAG clicked
  forever
    point towards [mouse-pointer v]
    move (10) steps
    next costume
    play drum (3 v) for (0.3) beats
    if <touching [herbert v]?>
      say [Caught you!] for (1) secs
    end
   end
```

##Kiểm tra dự án của bạn { .flag}

**Click the green flag.** (Click vào hình cờ màu xanh lá)

Felix có nói khi bắt được Herbert không?

##Lưu lại dự án của bạn { .save}

#**Step 4:**  Herbert biến thành 1 bóng ma khi bị bắt {.activity}

**Instead of Felix saying something, we want Herbert to turn into a ghost when he’s caught.** (Thay vì Felix nói gì đó, chúng tôi muốn Herbert biến thành bóng ma khi bị bắt)

##Bảng liệt kê các hoạt động cần kiểm tra { .check}

+ **Change Felix’s script to send this message when he catches Herbert:** (Thay đổi tập lệnh của Felix để gửi tin nhắn này khi bắt được Herbert)

```blocks
     when FLAG clicked
        forever
          point towards [mouse-pointer v]
          move (10) steps
          move (20) steps
          next costume
          play drum [3 v] for (0.3) beats
          if <touching [herbert v]?>
            broadcast [caught v]
            play drum [17 v] for (0.2) beats
            wait (1) secs
          end
        end
```

+ Thêm trang phục mới cho Herbert bằng cách chọn Herbert, vào phần Costumes, và click vào `Choose costume from Library button ` {.blocklightgrey}. Chọn trang phục **fantasy/ghost2-a**.

+ Chỉnh trang phục nhỏ hơn bằng cách click vào nó ở mục Paint Editor, và kéo hộp xuất hiện để chỉnh kích cỡ trang phục.

+ Đổi tên trang phục của Herbert để khi là chuột tên là "alive" (sống) và trang phục cho bóng ma tên "dead" (chết).
+ **Create a new script for Herbert to turn him into a ghost:** (Tại 1 tập lệnh mới cho Herbert để biến 1 bóng ma)

```blocks
  when I receive [caught v]
    switch costume to [dead v]
    wait (1) secs
    switch costume to [alive v]

```

##Kiểm tra dự án của bạn { .flag}

**Click the green flag.** (Click vào hình cờ màu xanh lá)

Herbert có biến thành ma khi bị bắt không? 
Felix có chơi đúng âm thanh ở thời điểm thích hợp không?
Felix có đứng yên đủ thời gian để Herbert chạy đi không? 

##Lưu lại dự án của bạn { .save}

#**Step 5:**  Giữ điểm {.activity}

**Hãy thêm 1 điểm để biết được chúng ta xuất sắc thê nào trong việc giữ Herbert còn sống.
Bắt đầu tính điểm ở mức 0 và tăng theo từng giây. Nếu Felix bắt được Herber, chúng ta sẽ giảm 100 điểm.**

##Bảng liệt kê các hoạt động cần kiểm tra { .check}

+ Tạo 1 biến, cho tất cả các hình sprit, gọi là Score. Click vào `Data` {.blockorange} ở menu phía trên, tạo 1 biến và đặt tên là `score` {.blockorange}, đảm bảo rằng "For all sprites" (tất cả các hình sprit) được chọn. 
+ **On the stage, create these two scripts:**


```blocks
when gf clicked
   set [score v] to [0]
   forever
      change [score v] by (1)
      wait (1) secs
   end

when I receive [caught v]
change [score v] by (-100)
```

##Kiểm tra dự án của bạn { .flag}

**Click the green flag.** (Click vào hình cờ màu xanh lá)

Điểm số có tăng lên theo từng giây không?
Điểm số có giảm đi 100 khi Herbert bị bắt không?
Điều gì xảy ra khi Herbert bị bắt trước khi điểm đạt 100? Điểm số có trở lại bằng 0 khi bạn bắt đầu 1 1 lượt chơi mới không? 

##Lưu lại dự án của bạn { .save}

**Well done you’ve finished, now you can enjoy the game!** (Rất tốt bạn đã hoàn thành, bây giờ có thể chơi rồi)

Đừng quên rằng bạn có thể chia sẽ trò chơi của mình với tất cả bạn bè và gia đình bằng cách click vào **Share** ở thanh menu!
