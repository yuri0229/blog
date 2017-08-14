##分析

杨辉三角的性质：第n层有n个值，如果用P(n, k)来表示n个字母中选择k个的组合方式，那么第n层的第k个值就是P(n-1, k-1)，如下图

第一层                 p(0, 0)

第二层         p(1, 0)         p(1, 1)

第三层 p(2, 0)         p(2, 1)         p(2, 2)

##PHP算法实现
```php
/* 计算阶乘 */
function T($n){
    if($n < 1){
        return 1;
    }
    return $n * T($n - 1);
}

/* 计算组合 */
function P($n, $k){
    return T($n) / T($n - $k) / T($k);
}

/* 打印n个tab */
function S($n){
    for($i=0; $i<$n; $i++){
        echo "\t";
    }
}

function Yh($n){
    for($i=0; $i<$n; $i++){
        S($n-$i-1);
        for($j=0; $j<=$i; $j++){
            echo P($i, $j)."\t\t";
        }
        echo "\r\n\r\n";
    }
}
Yh(5);
```
