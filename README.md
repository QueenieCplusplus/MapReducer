# MapReducer
Hadoop 運算架構 Divide & Conquer 分而治之

傳統的運算架構是集中處理，而現在未來趨勢相反，是將運算作為工作分散（發送）到儲存的資料上，然而這項技術很需要快速的網路 ～

* Map 工作節點對本機資料應用了 map() 函數

* Shuffle 重新分配

* Reduce 所有節點同時處理資料組




         Input Chunks ----->    x                                  /
                                                                  /
                                                                 /
                                y    ------>     (k, v) pairs    ------>    Combined Output
                                                                 \
                                                                  \
                                                                   \
                                z                               Tasks Reducer
                             Tasks Mapper


* Map 映射

利用映射產生列表

      Map(k1, v1) -> list(k2, v2)

* Reducer 減化

利用 Key Value 放到多個 node 中用撰寫的 Reducer 操作處理，歸併成一列表。

      Reduce(k2, list(v2)) -> list(v3)

* DataLocalization 資料在地化

      將分散於節點上的資料，就近處理，就是資料在地化處理（或稱資料當地語系化）。


