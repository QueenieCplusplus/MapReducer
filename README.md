# MapReducer

Hadoop 運算架構 Divide & Conquer 分而治之！

運算框架請詳見 Spark (可使用 Python)，
單純使用 Hadoop 則是僅支援 Java 和 C。

https://github.com/apache/hadoop （Java 後端程式設計師)

https://github.com/QueenieCplusplus/DataMining_Spark (Python 資料分析師)



         HDFS          Map ->  spill ->  Shuffle, copy and sort -> Reduce   ->   HDFS


         split1                                                                part1
         split2                                                                part2
         split3                                                                part3
  
  
* Split 將輸入的資料劃分成同等長度的小資料區塊 chunk -> split

* Shuddle 洗牌，指把 Map 的輸出匯入到 Reduce 的程式的過渡期。

傳統的運算架構是集中處理，而現在未來趨勢相反，是將運算作為工作分散（發送）到儲存的資料上，然而這項技術很需要快速的網路 ～




         Input Chunks ----->    x                                  /
                                                                  /
                                                                 /
                                y    ------>     (k, v) pairs    ------>    Combined Output
                                                                 \
                                                                  \
                                                                   \
                                z                               Tasks Reducer
                             Tasks Mapper
                             
* Map 工作節點對本機資料應用了 map() 函數

* Shuffle 重新分配

* Reduce 所有節點同時處理資料組                          
                             
-------------------------------------------------                             


* Map 映射

利用映射產生列表

      Map(k1, v1) -> list(k2, v2)

* Reducer 減化

利用 Key Value 放到多個 node 中用撰寫的 Reducer 操作處理，歸併成一列表。

      Reduce(k2, list(v2)) -> list(v3)

* DataLocalization 資料在地化

      將分散於節點上的資料，就近處理，就是資料在地化處理（或稱資料當地語系化）。


