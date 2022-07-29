# SM3 实现
关于sm3的实现，我们参考了CSDN上的文章，网上有很多SM3的源码，在此不多做解释，具体参见代码。
# SM3-Brithday-Attack
生日攻击建立在生日悖论上，我们对于n比特长的信息m，在2^n+1个数据中，至少能找到一对相等的数据；然而，要使我们从数据库中任意选出两个数据碰撞的概率接近100%，需要的数据量远比我们想象的要少。

通过对SM3的生日攻击，我们可以更好的确定SM3算法中哈希函数的输出长度。

在实现上，我们宏定义攻击长度n，我们任意选取两个信息m1和m2，不断尝试直到SM3(m1)与SM3(m2)的前n比特相等，即找到碰撞，输出相应的数据内容。通过改变长度n，对实验进行进一步研究。
# 运行结果与分析
碰撞前8bit

![OPED4A} 1GVSW6RZAZD) U](https://user-images.githubusercontent.com/71619888/181673179-b7b67adb-4174-47cf-8ace-bde0dedc397f.png)

碰撞前12bit

![R~(LNDZVZ9{P%$37FBK5MKS](https://user-images.githubusercontent.com/71619888/181673701-978f6269-15cc-4628-af98-1fbd4319d7c9.png)

碰撞前16bit

![}G HTK}A_ (%TL8JMO8K4UV](https://user-images.githubusercontent.com/71619888/181673282-db60a3a8-9def-4e40-9167-afea69cc8acc.png)

碰撞bit数较少的情况下，碰撞成功的几率比较高。

碰撞16bit耗时相比12bit的增加比12bit耗时相比8bit的增幅要大得多。
