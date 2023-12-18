# homework_lesson2
Провести настройку аутентификации доступа к yandex cloud-id,
введя в консоли:

export YC_TOKEN=$(yc iam create-token)

export YC_CLOUD_ID=$(yc config get cloud-id)

export YC_FOLDER_ID=$(yc config get folder-id)


Ввести в консоли команды:

Инициализация terraform

terraform init

Проверка сценария terraform

terraform plan

Будут созданы ВМ gfs, которая будет выполнять роль файлового хранилища с дополнительным диском,

который будет по iscsi подключен к ВМ web1, web2 и web3. На ВМ web1, web2 и web3 будет создана ФС gfs2.

Запустить сценарий создания ВМ

terraform apply

В консоле будут выведены 

внешние ip - external_ip_address_...

и внутренние ip - internal_ip_address_vm_...


В файле ya.yaml ввести external_ip_address для ВМ gfs, web1, web2 и web3


Проверить доступность ВМ с помощью модуля ping

ansible all -m ping

В файлах группоых переменных в group_vars/ ввести external_ip_address и nternal_ip_address

для ВМ gfs, web1, web2 и web3, а также iqn портала iscsi и пароль кластера psc


Проверить корректность синтаксиса плэйбука main.yaml

ansible-playbook --syntax-check main.yaml

Роль pcs_start выполняет установку ПО на web1, web2 и web3, создание и настройку pacemaker кластера,

а также настройку iqn на web1, web2 и web3

Роль target_start выполняет настройку портала iscsi на ВМ gfs

Роль gfs2_start выполняет настройку ФС gfs2 на web1, web2 и web3


Запускаем playbook на выполнение

ansible-playbook main.yaml



