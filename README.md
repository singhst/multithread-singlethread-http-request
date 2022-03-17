# multithread-vs-singlethread-python

## Multi-threading VS single-thread in HTTP request

Compare the time used by (1) multi-threading and (2) single-thread to request data from DATA.GOV.HK API.

Details please see the Jupyter Notebook.

---

Result:

|                     | multi-threading | single-thread |
|---------------------|-----------------|---------------|
| no. of Gov API call |      1,000      |      20       |
| time needs (second) |      15 s       |      13 s     |
| time per address    |    0.01484 s    |   0.810212 s  |

---

## Reference

Gov, data api to perform address lookup service:
* https://data.gov.hk/en-data/dataset/hk-ogcio-st_div_02-als/resource/b848308b-56ed-4be7-82e2-1df988a38c71

Python multi-threading & multi-processing:
* https://blog.floydhub.com/multiprocessing-vs-threading-in-python-what-every-data-scientist-needs-to-know/

