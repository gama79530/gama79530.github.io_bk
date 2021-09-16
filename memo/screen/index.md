<script src='https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.5/MathJax.js?config=TeX-MML-AM_CHTML'></script>
<script type="text/x-mathjax-config">
    MathJax.Hub.Config({ tex2jax: {inlineMath: [['$','$'], ['\\(','\\)']]} });
</script>
# 資源
- [使用 Screen 指令操控 UNIX/Linux 終端機的教學與範例](https://blog.gtwang.org/linux/screen-command-examples-to-manage-linux-terminals/)

# 指令格式
- screen [-opts] [cmd [args]]

# screen 常用參數
1. -ls
1. -r
1. -S
1. -d

# 常用熱鍵
1. ctrl-a + c
1. ctrl-a + d
1. ctrl-a + k
1. ctrl-a + " (shift + ')
1. ctrl-a + S (shift + s)
1. ctrl-a + Tab
1. ctrl-a + Q (shift + q)
1. ctrl-a + n
1. ctrl-a + p
1. ctrl-a + num (0 ~ 9)
1. ctrl-a + H (shift-h)

# 其他指令
1. pkill screen


# 重要路徑
1. log路徑 : $home\screenlog.x.txt
2. 密碼設定檔 : $home\.screenrc

# 安裝

        sudo apt-get update
        sudo apt-get install screen