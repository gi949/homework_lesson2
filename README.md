# homework_lesson2
ведя в консоли:

export YC_TOKEN=$(yc iam create-token)

export YC_CLOUD_ID=$(yc config get cloud-id)

export YC_FOLDER_ID=$(yc config get folder-id)


Ввести в консоли команды:

Инициализация terraform

terraform init

Проверка сценария terraform

terraform plan

Запустить сценарий создания ВМ

terraform apply

В консоле будут выведены 

внешние ip - external_ip_address_...

и внутренние ip - internal_ip_address_vm_...


В файле ya.yaml ввести external_ip_address_vm_1 для vm-1:

vm-1 ansible_host=<external_ip_address_vm_1>

Проверить доступность vm-1 с помощью модуля ping

ansible  -m ping

Проверить корректность синтаксиса плэйбука task.yaml

ansible-playbook --syntax-check task.yaml


ansible-playbook task.yaml



