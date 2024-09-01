# LeetCode_2024.9.1_OQPD
每日一题

---

# 3217.构造相同颜色的正方形（简单）

给你一个二维 3 x 3 的矩阵 grid ，每个格子都是一个字符，要么是 'B' ，要么是 'W' 。字符 'W' 表示白色，字符 'B' 表示黑色。

你的任务是改变 至多一个 格子的颜色，使得矩阵中存在一个 2 x 2 颜色完全相同的正方形。

如果可以得到一个相同颜色的 2 x 2 正方形，那么返回 true ，否则返回 false 。

![image](https://github.com/user-attachments/assets/81716f86-e224-436b-af60-fca9dc67a22a)

![image](https://github.com/user-attachments/assets/530db9e2-221e-4a0e-a0c7-73419a2a4adc)

![image](https://github.com/user-attachments/assets/561af15a-b475-47b3-85c6-fc5b7d369984)

---

code:
```Java
class Solution {
    public boolean canMakeSquare(char[][] grid) {
        for (int i = 0; i <= 1; i++) {
            for (int j = 0; j <= 1; j++) {
                if (check(grid, i, j)) {
                    return true;
                }
            }
        }
        return false;
    }

    public boolean check(char[][] grid, int x, int y) {
        int count = 0;
        for (int i = 0; i <= 1; i++) {
            for (int j = 0; j <= 1; j++) {
                if (grid[x + i][y + j] == 'B') {
                    count++;
                }
            }
        }
        return count != 2;
    }
}
```
---

以前没怎么见过像“return count != 2”的返回判断语句，感觉挺有意思。
