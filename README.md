# multithread-vs-singlethread-python

P.S. 
1. [May by better to use `asynchronous` --> prevent race condition (competing the a shared variable / same resources)](https://poe.com/s/4Lt3eBg21WbzA4LTiWnI)
2. [Add `thread lock` to prevent race condition](https://ithelp.ithome.com.tw/articles/10221065)
3. [Use thread-safe data structure: thread lock, `queue.Queue()`](https://poe.com/s/8hXhjPiPb6H8J8kukBc8)
4. [solve "call api too frequently, connection fail issue"](https://blog.csdn.net/weixin_34232617/article/details/89192813?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-89192813-blog-107109614.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1-89192813-blog-107109614.pc_relevant_default&utm_relevant_index=1)

## Multi-threading VS single-thread in HTTP request

Compare the time used by (1) multi-threading and (2) single-thread to request data from DATA.GOV.HK API.

Multi-threading much much much outperforms single-threading in Network or I/O bound task. Multi-threading finishes 1,000 requests in 15s, but single-threading completes only 20 reqeusts in ~15s.

Details please see the Jupyter Notebook.

---

Result:

|                     | multi-threading | single-thread |
|---------------------|-----------------|---------------|
| no. of Gov API call |      1,000      |      20       |
| time needs (second) |      15 s       |      13 s     |
| time per a call     |    0.01484 s    |   0.810212 s  |

---

## Reference

Gov, data api to perform address lookup service:
* https://data.gov.hk/en-data/dataset/hk-ogcio-st_div_02-als/resource/b848308b-56ed-4be7-82e2-1df988a38c71
* Doc => https://data.gov.hk/en-data/dataset/hk-ogcio-st_div_02-als => https://www.als.ogcio.gov.hk/docs/Data_Dictionary_for_ALS_EN.pdf 

Python multi-threading & multi-processing:
* https://blog.floydhub.com/multiprocessing-vs-threading-in-python-what-every-data-scientist-needs-to-know/

Race conditions and deadlocks:
* https://learn.microsoft.com/en-us/troubleshoot/developer/visualstudio/visual-basic/language-compilers/race-conditions-deadlocks
