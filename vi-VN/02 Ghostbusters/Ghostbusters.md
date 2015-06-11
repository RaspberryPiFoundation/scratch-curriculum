---
title: Ghostbusters
level: Level 1
language: en-GB
stylesheet: scratch
embeds: "*.png"
note: "notes for club leaders.md"
...

# Giới thiệu { .intro}
Dự án này gần giống trò chơi __Đập chuột__. Bạn ghi điểm khi đánh con ma xuất hiện trên màn hình. Mục tiêu là ghi thật nhiều điểm trong thời gian 30 giây.

![screenshot](ghostbsuters_screenshot.png)

#BƯỚC 1: Tạo hình bóng ma di chuyển { .activity}

## Bảng liệt kê hoạt động { .check}

+ Bắt đầu dự án mới bằng cách ấn biểu tượng __Start a new scratch project__
+ __Xóa hình con mèo trên màn hình__ và thay bởi hình nền __Nature/woods (Thiên nhiên)__.
+ Ấn vào biểu tượng ‘Choose sprite from library’ để thêm hình con ma mới (ghoul) cho dự án (Sử dụng tạo hình __Fantasy/Ghost1__).

__Bây giờ, chúng ta cần làm cho con ma di chuyển__

+ Thêm một “Variable” (“Biến”) cho riêng hình con ma, gọi là ‘speed’ (Tốc độ)
Trên __Stage__ (Màn hình chơi), hộp điều khiển biến này phải hiện “__Ghost1 speed__”.
Nếu nó chỉ hiện tên “Speed”, xóa variable này và làm lại (Chỉ cho riêng hình con ma). Bỏ tick ô vuông bên cạnh hộp speed trong phần __Data palette__ để nó không hiện trên màn hình chơi.

Biến speed điều khiển tốc độ di chuyển của con ma. Chúng ta dùng một biến mà có thể giúp thay đổi độ di chuyển nhanh chậm của con ma khi trò chơi bắt đầu.

+Chúng ta muốn con ma bắt đầu di chuyển khi trò chơi bắt đầu, nên __viếts cript như sau__:

```blocks

    when FLAG clicked
    set [speed v] to [5]
    forever
        move (speed) steps
```
        
##Kiểm tra lại { .flag}
__Ấn vào lá cờ màu xanh__ và xem hoạt động của con ma. Tại sao nó bị kẹt ở rìa màn hình?

## Bản liệt kê hoạt động { .check}

+ Để ngừng việc con mà bị kẹt, chúng ta cần khiến nó quay trở lại lối vào khác từ rìa màn hình. Chỉnh sửa bản script cũ của bạn bằng việc thêm hộp “If on edge, bounce’ dưới ‘move’, ‘speed’ và ‘step’.

```blocks

    when FLAG clicked
    set [speed v] to [5]
    forever
        move (speed) steps
        if on edge, bounce
```
+ Để ngừng việc con ma quay ngược đầu, ấn vào ‘rotation style: left-right’ ở phần Sprite Summary.

##Kiểm tra lại { .flag}
__Ấn vào cá cờ màu xanh__
Con ma có di chuyển qua lại trên màn hình không?

##Lưu lại công việc của bạn { .save}

##Có thể thử thêm { .try}

+ __Thử thay đổi giá trị của biến speed để làm con ma bay nhanh hay chậm hơn
+ __Làm thế nào để khiến con ma tăng tốc dần?__
(Việc này hơi khó, bạn không phải lo lắng nếu không làm được)
Bạn sẽ có thêm nhiều mẹo trong quá trình làm dự án này)


#BƯỚC 2: Làm con ma xuất hiện và biến mất bất chợt { .activity}

Để trò chơi thêm thú vị, chúng ta có thể khiến con ma xuất hiaanj và biến mất bất ngờ. Chúng ta sẽ làm vậy với một bản script khác chạy song song với sự di chuyển của con ma. Nội dung của bản script mới này là giấu hình con ma đi một cách ngẫu nhiên, rồi lại hiện hình trở lại ngẫu nhiên, và lặp đi lặp lại.

## Bản liệt kê hoạt động { .check}

__Tạo bản script này cho con ma:__

```blocks

    when FLAG clicked
    forever
        hide
        wait (pick random (2) to (5)) secs
        show
        wait (pick random (3) to (5)) secs

```
##Kiểm tra lại { .flag}
__Ấn vào biểu tượng lá cờ màu xanh__ 
Con ma có di chuyển qua lại và biến mất rồi xuất hiện ngẫu nhiên trên màn hình?

##Lưu lại công việc của bạn { .save}

##Có thể thử thêm{ .try}
+ __Thử thay đổi thời gain. Chuyện gì xảy ra nếu bạn chọn số rất lớn/ rất nhỏ?__
(Việc này co cho bạn gợi ý nào về cách làm con ma tăng tốc dần?)


#BƯỚC 3: Làm cho con ma biến mất khi người chơi click vào { .activity}

Để chuyển thành một trò chơi, chúng ta cần cho người chơi một công cụ chơi. Họ cần click vào con ma để khiến nó biến mất. Khi người chơi clock vào con ma, chúng ta muốn nó biến mất và tạo ra âm thanh.

## Bản liệt kê hoạt động { .check}

+ Trong phần __Sounds__, thêm âm thanh mới __Electronuc/fairydust__, sử dụng nút ‘Choose sound from library’.
+ __Thêm phần script này cho con ma:__

```blocks

    when this sprite clicked
    hide
    play sound [Fairydust v]
```
##Kiểm tra lại { .flag}
__Ấn vào biểu tượng lá cờ màu xanh.__ 
Con ma có biến mất và tạo ra âm thanh khi bạn click vào nó?

##Lưu lại công việc của bạn { .save}

##Có thể thử thêm { .try}
+ __Hỏi tình nguyện viên liệu bạn có thể tự thu âm thanh riêng của mình không.__

#BƯỚC 4: Thêm điểm số và thời gian { .activity}

Chúng ta đã có con ma, nhưng giờ chúng ta muốn tạo trò chơi! Chúng ta muốn điểm số được khi lại mỗi khi người chơi click bào con ma, đồng thời giới hạn thời gian cho trò chơi. Chúng ta có thể dùng một viến khác cho điểm số và thời gian.

## Bản liệt kê hoạt động { .check}

+ Thêm một ‘Variable’ mới cho tất cả các hình sprite, gọi là __score__, rồi thay thế script cho con ma để thêm biến này khi người chơi click vào con ma.


```blocks

    when this sprite clicked
    hide
    play sound [Fairydust v]
    change [score v] by (1)
```

+Chuyển sang __Stage__ và tạo __Biến mới__ gọi là __timer__. Thêm script để lập thời gian là __30__ và khởi động lại score về __0__. Sau đó, dùng ‘repeat until’ rồi giảm ‘timer’ 1 (change timer by -1). Việc này cần lặp đi lặp lại cho đến khi timer bằng 0. Tại thời điểm này, dùng ‘stop all’ để dừng trò chơi.


```blocks

    when FLAG clicked
    set [timer v] to (30)
    set [score v] to (0)
    repeat until <(timer) = [0]>
        wait (1) secs
        change [timer v] by (-1)
    
    stop [all v]
```


##Kiểm tra lại { .flag}
__Click vào biểu tượng lá cờ màu xanh.__ 

##Lưu công việc của bạn { .save}

##Có thể thử thêm { .try}
1. __Làm thế nào để con ma tăng tốc trong quá trình chơi?__
2. __Tốt lắm! Bạn đã làm xong trò chơi cơ bản. Có nhiều thứ khác bạn có thể làm thêm cho trò chơi này. Hãy tự khám phá!__

##Thử thách: Thêm ma { .challenge}
Nếu một con ma đã tốt, nhiều hơn càng tốt hơn! __Hãy tạo ba con ma di chuyển.__
1. Nhân bản các con ma bằng __click chuột phải__ vào danh sách hình sprite.
2. Với mỗi con ma, __điều chỉnh kích cỡ__ để các con ma to nhỏ khác nhau.
3. Với mỗi con ma, thay đổi __biến speed__ để chúng bay với tốc độ khác nhau
4. Di chuyển các con ma xung quanh để chúng không bay cùng chỗ

##Kiểm tra lại { .flag}
__Click vào biểu tượng lá cờ xanh.__ 
Bạn có ba con ma di chuyển qua lại màn hình, xuất hiện và biến mất ngẫu nhiên, và biến mất mỗi khi bạn click vào không?


##Lưu lại { .save}

##Có thể thử thêm { .try}

1. __Bao nhiêu bóng ma là đủ?__
2. __Bạn có thể làm cho những con ma trông khác nhau không? Bạn nên chỉnh sửa phần costume, hoặc sử dụng các block trong phần ‘Looks palette’ cho việc này.__
3. __Bạn có thể gắn giá trị điểm khác nhau cho mỗi con ma? Ví dụ, làm con ma bay nhanh nhất (và kích thước nhỏ nhất) ứng với 10 điểm?__


__Tốt lắm! Bạn đã hoàn thành. Giờ bạn có thể thưởng thức trò chơi rồi__
Đừng quên bạn có thể chia sẻ trò chơi của mình với bạn bè và gia đình bằng cách click vào __Share__ trên thanh menu!
