## 查看所有ns
```
$ kubectl get ns
```

## 查看所有namespace下的pod
```
$ kubectl get po -A
```

## 建立Namespace
```
$ kubectl create namespace my-namespace
```

## 另一個建立方法
```
$ cd C:\K8s_nscode\hellospace
$ docker build -t springio-demo .

$ cd ..
$ kubectl apply -f base
```

## 查看所有ns 增加 my-namespace hellospace
```
$ kubectl get ns
```

## 創建完之後，可用 kubectl get 查看在 hellospace 裡的 Resource Quotas
```
$ kubectl get resourcequotas -n hellospace
```
## 查看 compute-quotas 與 object-quotas 的內容
```
$ kubectl describe resourcequotas compute-quotas -n hellospace
$ kubectl describe resourcequotas object-quotas -n hellospace
```

## 測試可否建立另一個服務
```
$ kubectl apply -f mysql
```

## 調整後重新測試
```
$ kubectl apply -f base
$ kubectl apply -f mysql
```

## 查看 compute-quotas 與 object-quotas 的內容
```
$ kubectl describe resourcequotas compute-quotas -n hellospace
$ kubectl describe resourcequotas object-quotas -n hellospace
```

## 刪除單一 Namespaces
```
$ kubectl delete namespaces hellospace
```