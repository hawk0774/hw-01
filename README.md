# Домашнее задание к занятию «Введение в Terraform»
### Задание 1
![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_14.png)
1. Перейдите в каталог [**src**](https://github.com/netology-code/ter-homeworks/tree/main/01/src). Скачайте все необходимые зависимости, использованные в проекте.
 ![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_2.png)
2. Изучите файл **.gitignore**. В каком terraform-файле, согласно этому .gitignore, допустимо сохранить личную, секретную информацию?(логины,пароли,ключи,токены итд)
![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_1.png)

-В файле .terraformrc допустимо хранить, так как он попадает в исключение !.terraformrc.-

4. Выполните код проекта. Найдите  в state-файле секретное содержимое созданного ресурса **random_password**, пришлите в качестве ответа конкретный ключ и его значение.
![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_3.png)
5. Раскомментируйте блок кода, примерно расположенный на строчках 29–42 файла **main.tf**.
 
Выполните команду ```terraform validate```. Объясните, в чём заключаются намеренно допущенные ошибки. Исправьте их.
![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_4.png)

![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_5.png)

5. Выполните код. В качестве ответа приложите: исправленный фрагмент кода и вывод команды ```docker ps```.

![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_5.png)

![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_6.png)

![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_7.png)

![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_8.png)
 
6. Замените имя docker-контейнера в блоке кода на ```hello_world```. Не перепутайте имя контейнера и имя образа. Мы всё ещё продолжаем использовать name = "nginx:latest". Выполните команду ```terraform apply -auto-approve```.
 
Объясните своими словами, в чём может быть опасность применения ключа  ```-auto-approve```. Догадайтесь или нагуглите зачем может пригодиться данный ключ? В качестве ответа дополнительно приложите вывод команды ```docker ps```.
![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_9.png)

![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_10.png)
Данный ключ минует этап проверки перед запуском конфигурации, тот этап где можно увидеть изменения вносимые и остановиться. Пригодиться может в скриптах и прочих автоматизациях или в тестировании.

7. Уничтожьте созданные ресурсы с помощью **terraform**. Убедитесь, что все ресурсы удалены. Приложите содержимое файла **terraform.tfstate**.

![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_11.png)

![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_13.png)
 
8. Объясните, почему при этом не был удалён docker-образ **nginx:latest**. Ответ **ОБЯЗАТЕЛЬНО НАЙДИТЕ В ПРЕДОСТАВЛЕННОМ КОДЕ**, а затем **ОБЯЗАТЕЛЬНО ПОДКРЕПИТЕ** строчкой из документации [**terraform провайдера docker**](https://docs.comcloud.xyz/providers/kreuzwerker/docker/latest/docs).  (ищите в классификаторе resource docker_image )

-Атрибут keep_locally = true в ресурсе docker_image указывает Terraform не удалять Docker-образ nginx:latest из локального хранилища Docker даже в случае, если ресурс docker_image.nginx_image будет удалён из состояния Terraform.-
![alt text](https://raw.githubusercontent.com/hawk0774/hw-01/main/Screenshot_12.png)
