* * *

назва: Війни Клонів рівень: Scratch 2 мова: uk стильове оформлення: scratch додатки: "*.png" матеріали: ["Засоби керівників клубу/*"] тестова версія: підтвердженно ...

## Проект за сприяння спільноти {.challenge.pdf-hidden}

Цей проект був створений за допомогою Erik. Якщо ви хочете зробити внесок у вигляді власного проекту, зв'яжіться з нами на Github..

# Передмова {.intro}

У цьому проекті ви навчитеся як створити гру, в якій ви маєте врятувати Землю від космічних монстрів.

<div class="scratch-preview">
  crwMD_Iframe_0 <img src="invaders-final.png" />
</div>

# Крок 1: Створення космічного корабля {.activity}

Давайте зробимо корабель, який захистить Землю!

## Завдання для виконання {.check}

+ Почніть новий Scratch проект і видаліть спрайт кота так щоб ваш проект став пустий. Ви можете знайти онлайн Scratch-редактор на jumpto.cc/scratch-new.

+ Додайте задник 'stars' (зірки) і спрайт 'Spaceship' (космічний корабель) до вашого проекту. Зменшіть корабель та пересуньте його до низу екрану.
    
    ![screenshot](invaders-sprites.png)

+ Додайте код для пересування корабля вліво при натисканні клавіши зі стрілкою вліво. Вам треба використати ці блоки:
    
    ```blocks
    коли натиснуто ⚑
    завжди
       if <key [стрілка вліво v] pressed?> then
            змінити x на (-4)
        end
    end
```

+ Додайте код для пересування вашого корабля вправо при натисканні клавіші зі стрілкою вправо.

+ Протестуйте свій проект з метою перевірити чи ви можете керувати кораблем за допомогою клавіш зі стрілками.

## Збережіть свій проект {.save}

# Крок 2: Блискавки {.activity}

Дайте своєму космічному кораблю можливість стріляти блискавками!

## Завдання для виконання {.check}

+ Додайте спрайт 'Lightning' (блискавка) з Scratch бібліотеки. Клікніть на спрайт у редакторі убрання та переверніть блискавку.
    
    ![screenshot](invaders-lightning.png)

+ При запуску гри блискавка повинна бути прихована поки корабель не стріляє зі своїх лазерних гармат.
    
    ```blocks
    коли натиснуто ⚑
    сховати
```

+ Додайте наступний код **до Космічного корабля** щоб при натисканні пробілу створювалась блискавка.
    
    ```blocks
    коли натиснуто ⚑
    завжди
        if <key [пропуск v] pressed?> then
            створити клон з [Lightning v]
        end
    end
```

+ У випадку створення нового клону (блискавки), він повинен з'явитися у тому ж місці, що й корабель, а потім рухатися по екрану допоки не торкнеться краю. Додайте наступний код **до Блискавки**
    
    ```blocks
    коли я починаю як клон
    перемістити в [Spaceship v]
    показати
    repeat until <touching [межа v] ?>
        змінити y на (10)
    end
    вилучити цей клон
```

Примітка: Новий клон пересувається до космічного корабля поки його не видно, і лише потім показується. Так воно виглядає краще.

+ Протестуйте свою блискавку натиснувши на пробіл.

## Збережіть свій проект {.save}

## Виклик: Виправте блискавку {.challenge}

Що трапиться якщо затримаєте пробіл натиснутим? Чи можете ви використати `wait`{.blockcontrol} - блокування, щоб виправити ситуацію?

## Збережіть свій проект {.save}

# Крок 3: Літаючі Космічні бегемоти {.activity}

Давайте додамо безліч літаючих бегемотів, які намагаються знищити ваш корабель.

## Завдання для виконання {.check}

+ Create a new sprite from the 'Hippo1' image in the Scratch library.
    
    ![screenshot](invaders-hippo.png)

+ Set its rotation style to be left-right only, and add the following code to hide the sprite when the game starts:
    
    ```blocks
    коли натиснуто ⚑
    сховати
```

+ Create a new variable called `speed` {.blockdata}, that is for the hippo sprite only.
    
    ![screenshot](invaders-var.png)
    
    You'll know if you've done this correctly because the variable will have the name of the sprite next to it, like this:
    
    ![screenshot](invaders-var-test.png)

+ The following code will create a new hippo every few seconds. **The Stage** is a good place for this code to live:
    
    ```blocks
    коли натиснуто ⚑
    завжди
        чекати (випадкове від (2) до (4)) секунд
        створити клон з [Hippo1 v]
    end
```

+ When each hippo clone starts, make it move around the stage (at a random speed) until it gets hit by the lightning. Add this code **to the hippo** sprite:
    
    ```blocks
    коли я починаю як клон
    встановити [speed v] в (випадкове від (2) до (4))
    перемістити в x:(випадкове від (-220) до (220)) y:(150)
    показати
    repeat until <touching [lightning v] ?>
        перемістити на (speed) кроків
        поворот ↻ (випадкове від (-10) до (10)) градусів
        відбивати від меж
    end
    вилучити цей клон
```

+ Test out your hippo code. You should see a new hippo clone appear every few seconds, each moving at its own speed.
    
    ![screenshot](invaders-hippo-test.png)

+ Test your laser cannon. If you hit a hippo, does it vanish?

+ When a hippo touches your spaceship, we need to make the spaceship explode! To do this, first make sure that your spaceship has 2 costumes called 'normal' and 'hit'.
    
    ![screenshot](invaders-spaceship-costumes.png)
    
    The spaceship's 'hit' costume can be made by importing the 'Sun' image from the Scratch library, and using the 'Color a shape' tool to change its colour.
    
    ![screenshot](invaders-sun.png)

+ Add this code to your spaceship so that it switches costume whenever it collides with a flying hippo:
    
    ```blocks
    коли натиснуто ⚑
    завжди
        змінити образ на [normal v]
        wait until <touching [Hippo1 v] >?
        змінити образ на [hit v]
        оповістити [hit v]
        чекати (1) секунд
    end
```

+ Did you notice that you have broadcast a 'hit' message in the code above? You can use this message to make all of the hippos disappear when the spaceship is hit.
    
    Add this code to your hippo:
    
    ```blocks
    коли одержую [hit v]
    вилучити цей клон
```

+ Test out this code by starting a new game and colliding with a hippo.
    
    ![screenshot](invaders-hippo-collide.png)

## Збережіть свій проект {.save}

## Виклик: Життя та Рахунок {.challenge}

Can you add a `lives` {.blockdata}, `score` {.blockdata} or even a `highscore` {.blockdata} to your game? You can use the 'Catch the Dots' project to help you.

## Збережіть свій проект {.save}

# Step 4: Fruit Bats! {.activity}

Let's make a fruit bat that throws oranges at your spaceship.

## Завдання для виконання {.check}

+ Firstly, make a new bat sprite that will `move` {.blockmotion} across the top of the stage `forever` {.blockcontrol}. Remember to test out your code.
    
    ![screenshot](invaders-bat.png)

+ If you look at the bat's costumes, you'll see that it already has 2:
    
    ![screenshot](invaders-bat-costume.png)
    
    Use the `next costume` {.blocklooks} block to make the bat flap its wings as it moves.

+ Create a new 'Orange' sprite from the Scratch library
    
    ![screenshot](invaders-orange.png)

+ Add code to your bat, so that it creates a new orange clone every few seconds.
    
    ```blocks
    коли натиснуто ⚑
    завжди
        чекати (випадкове від (5) до (10)) секунд
        створити клон з [Orange v]
    end
```

+ Click on your orange sprite and add this code to make each orange clone drop down the stage from the bat towards the spaceship:
    
    ```blocks
    коли натиснуто ⚑
    сховати

    коли я починаю як клон
    перемістити в [Bat1 v]
    показати
    repeat until <touching [межа v] ?
        змінити y на (-4)
    end
    вилучити цей клон

    коли одержую [hit v]
    вилучити цей клон
```

+ In your spaceship sprite, you'll need to modify your code so that you are hit if you touch a hippo or an orange:
    
    ```blocks
    wait until < <touching [Hippo1 v]?> or <touching [Orange v]?>>
```

+ Test your game. What happens if you get hit by a falling orange?

## Збережіть свій проект {.save}

# Step 5: Game over {.activity}

Let's add a 'game over' message at the end of the game.

## Завдання для виконання {.check}

+ If you haven't already, create a new variable called `lives` {.blockdata}. Your spaceship should start with 3 lives and lose a life whenever it collides with an enemy. Your game should also stop when you run out of lives. If you need help, you can use the 'Catch the Dots' project to help you.

+ Draw a new sprite called 'Game Over', using the text tool.
    
    ![screenshot](invaders-game-over.png)

+ On your stage, broadcast a `game over` {.blockevents} message just before the game ends.
    
    ```blocks
    оповістити [game over v] і чекати
```

+ Add this code to your 'Game Over' sprite, so that the message shows at the end of the game:
    
    ```blocks
    коли натиснуто ⚑
    сховати

    коли одержую [game over v]
    показати
```

Because you've used a `broadcast [game over] and wait` {.blockevents} block on your stage, it will wait for the 'Game Over' sprite to be displayed before ending the game.

+ Test your game. How many points can you score? Can you think of ways to improve your game if it is too easy or too hard?

## Збережіть свій проект {.save}

## Challenge: Improve your game {.challenge}

What improvements can you make to your game? Here are some ideas: + Add health packs that you can collect to gain extra lives;

![screenshot](invaders-aid.png)

+ Add floating rocks that your spaceship must avoid;

![screenshot](invaders-rocks.png)

+ Make more enemies appear when your score gets to 100.

```blocks
    wait until <(score) = [100]>
```

## Збережіть свій проект {.save}