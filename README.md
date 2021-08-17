# alex3030k_platform
alex3030k Platform repository

Когда запускается kubelet, он сканирует известные ему пути и автоматически запускает статические Pods.
Работающий kubelet периодически сканирует каталоги на предмет изменений и в соответствии с ними добавляет/удаляет Pods
Одним из зарегистрированных путей является
/etc/kubernetes/manifests
Где расположены:
etcd.yaml
kube-apiserver.yaml
kube-controller-manager.yaml
kube-scheduler.yaml

Ключ 
/registry/deployments/kube-system/coredns
расположен в etcd
и с ним кубер работает как с другими Pod

1)Создал локально Dockerfile на основе образа nginx:1.21.1
внес необходимые изменения и залил новый образ hub.docker.com
2)Выполнил все необходимые действия описанные в файле ДЗ
3)Скачал HipsterShop
При сборке frontend\Dockerfile вылезли проблемы с DNS
Обошел их небольшим изменением в Dockerfile
 Пример
RUN echo "nameserver 8.8.8.8" > /etc/resolv.conf &&\
 apk add --no-cache ca-certificates git
 Собрал его и залил к себе в репозиторий
 Причина почему frontend находится в статусе Error
не были установлены
 Переменные окружения контейнера
Пример 
  env:
     - name: PRODUCT_CATALOG_SERVICE_ADDR
       value: "productcatalogservice:3550"
