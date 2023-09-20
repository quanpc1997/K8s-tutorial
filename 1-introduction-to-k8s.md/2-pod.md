# II. Pod và YAML
## 1. Pod 
Trong Docker thì container là thành phần nhỏ nhất thì Pod là thành phần nhỏ nhất trong k8s cluster. Để K8s có thể điều khiển được Docker thì nó sẽ tạo ra một pod object bao bọc container đó. 

Thông thường một Pod chỉ chứa một container duy nhất. Khi muốn scale lên thì người ta sẽ tạo ra nhiều pod khác nhau. Nhưng cũng có một số trường hợp, 2 container sẽ được tạo trong cùng 1 Pod. Với 1 container là container chính và container còn lại sẽ đóng vai trò là hỗ trợ container chính. Trong trường hợp này khi tạo pod thì cả 2 container sẽ cùng được tạo và khi xóa pod thì cả 2 đều bị xóa.

**Command**
- Tạo một pod.
```sh
kubectl run nginx --image nginx
```

- Xem danh sách các pod đang chạy
```sh
kubectl get pods
```

- Lấy thông tin chi tiết của từng pod
```sh
kubectl describe pod nginx
```

- Để xóa một pod đang chạy
```sh
kubectl delete pod nginx
```

## 2. YAML in K8s
Trong một file YAML bắt buộc cần có các trường sau:
```yaml
apiVersion:
kind:
metadata:

spec:



```
![YAML file in K8s](/1-introduction-to-k8s.md/images/3-yaml-in-k8s.png)
Hình bên trái là một ví dụ về file yaml. Với các giá trị của kind và apiVersion tương ứng ở bảng bên phải. Trong đó lưu ý là các giá trị của apiVersion và kind là kiểu string. Các giá trị trong metadata là kiểu dictionary. Container in List/Array. 

Ngoài ra trước trường có dấu "-" tức là nó đang đánh dấu rằng đó là một phần tử trong 1 list. Các trường không có dấu "-" phía trước được tính là các từ khóa đơn.

- Để chạy file yaml trong K8s.
```sh
kubectl create -f ten_file.yaml
```