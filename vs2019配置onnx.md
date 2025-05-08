# 1.使用dml来加速推理

```c++
OrtStatus* status = OrtSessionOptionsAppendExecutionProvider_DML(sessionOptions, 0);
```

# 2.vs2019配置onnxruntime环境

> https://blog.csdn.net/caip12999203000/article/details/125516627?ops_request_misc=%7B%22request%5Fid%22%3A%22170193457416800180627787%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=170193457416800180627787&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~baidu_landing_v2~default-4-125516627-null-null.142^v96^pc_search_result_base9&utm_term=VS onnxruntime&spm=1018.2226.3001.4187
