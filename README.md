# Домашнее задание к занятию Troubleshooting

### Цель задания

Устранить неисправности при деплое приложения.

### Чеклист готовности к домашнему заданию

1. Кластер K8s.

### Задание. При деплое приложение web-consumer не может подключиться к auth-db. Необходимо это исправить

1. Установить приложение по команде:
```shell
kubectl apply -f https://raw.githubusercontent.com/netology-code/kuber-homeworks/main/3.5/files/task.yaml
```
2. Выявить проблему и описать.
3. Исправить проблему, описать, что сделано.
4. Продемонстрировать, что проблема решена.

**Пытаемся установить приложение, создаём необходимые namespaces, проверяем что поднялось:**

<p align="center">
    <img width="1200 height="600" src="/img/ts_add_ns_apply_f.png">
</p>

**Проверяем доступ из пода в web к кластеру в data по ip:**

<p align="center">
    <img width="1200 height="600" src="/img/ts_data_pod_ip_curl.png">
</p>

**Проверяем логи пода в web:**

<p align="center">
    <img width="1200 height="600" src="/img/ts_data_pod_trouble_logs.png">
</p>

**Изменяем имя приложения, к которому происходит обращение, на полное dns-name, в деплойменте web-consumer:**

<p align="center">
    <img width="1200 height="600" src="/img/ts_data_pod_name_change.png">
</p>

**Применяем обновлённую версию деплоймента web-consumer, проверяем доступ из пода в web:**

<p align="center">
    <img width="1200 height="600" src="/img/ts_data_pod_name_curl.png">
</p>

**Проверяем логи:**

<p align="center">
    <img width="1200 height="600" src="/img/ts_data_pod_logs.png">
</p>


### Правила приёма работы

1. Домашняя работа оформляется в своём Git-репозитории в файле README.md. Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.
2. Файл README.md должен содержать скриншоты вывода необходимых команд, а также скриншоты результатов.
3. Репозиторий должен содержать тексты манифестов или ссылки на них в файле README.md.
