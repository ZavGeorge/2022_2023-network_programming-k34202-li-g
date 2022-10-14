University: [ITMO University](https://itmo.ru/ru/) <br/>
Faculty: [FICT](https://fict.itmo.ru) <br/>
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming) <br/>
Year: 2022/2023 <br/>
Group: K34202 <br/>
Author: Li Galina <br/>
Lab: Lab2 <br/>
Date of create: 06.10.2022 <br/>
Date of finished: x.10.2022 <br/>

# Лабораторная работа №2 "Развертывание дополнительного CHR, первый сценарий Ansible"

## Описание
   В данной лабораторной работе на практике изучается система управления конфигурацией Ansible, использующаяся для автоматизации настройки и развертывания программного обеспечения.

## Цель работы:
   С помощью Ansible настроить несколько сетевых устройств и собрать информацию о них. Правильно собрать файл Inventory.

## Ход работы:
   В процессе выполнения лабораторной работы были выпонены следующие шаги:
   
   ### Создание виртуальной машины на VirtualBox, установка CHR, организация OVPN-клиента ###
   
   1. Была создана виртуальная машина CHR_2 на VirtualBox.
   2. Был получен IP-адрес ВМ.
 
      [<img src="https://user-images.githubusercontent.com/58363643/194368638-c09ea438-c855-4186-ba90-3c5b8cec3f70.png" width="400"/>](https://user-images.githubusercontent.com/58363643/194368638-c09ea438-c855-4186-ba90-3c5b8cec3f70.png)
 
   3. Были получены сертификат и ключ для OVPN-клиента mikrotic2. В WInBox были имортированы сертификат и ключ, настроен OзoenVPN-клиент.
   
      [<img src="https://user-images.githubusercontent.com/58363643/194483645-8d4def2c-4624-4226-8cb6-ee9f388117ba.png" width="400"/>](https://user-images.githubusercontent.com/58363643/194483645-8d4def2c-4624-4226-8cb6-ee9f388117ba.png)

   4. Проверена IP-связность между OVPN-сервером и СHR_2.
  
      [<img src="https://user-images.githubusercontent.com/58363643/194484729-7ca4c125-9226-4e5e-be35-cff2f26565b0.png" width="400"/>](https://user-images.githubusercontent.com/58363643/194484729-7ca4c125-9226-4e5e-be35-cff2f26565b0.png)
      
   ### Настройка CHR-машин с помощью Ansible

   5. Был настроен файл инвентаризации /etc/ansible/host.
      
      ```
      ansible-inventory --list -y
      ```
      [<img src="https://user-images.githubusercontent.com/58363643/194758918-07f5e987-d0a3-4084-901e-c6035c49a398.png" width="500"/>](https://user-images.githubusercontent.com/58363643/194758918-07f5e987-d0a3-4084-901e-c6035c49a398.png)

   7. Произведена проверка подключения.
   
      ```
      ansible all -m ping
      ```
      [<img src="https://user-images.githubusercontent.com/58363643/194758473-81a7018d-a803-4504-af01-267ff3425532.png" width="200"/>](https://user-images.githubusercontent.com/58363643/194758473-81a7018d-a803-4504-af01-267ff3425532.png)
      
      ![image](https://user-images.githubusercontent.com/58363643/195847727-0e73cc19-5d92-44ae-af6b-4d5dfd2d7d25.png)

      ![image](https://user-images.githubusercontent.com/58363643/195847578-98733f0e-5f6f-447d-8b01-743dee600202.png)
      
      ![image](https://user-images.githubusercontent.com/58363643/195847651-3270f471-2f5e-4384-a1a6-769e0faa17a4.png)

      ![image](https://user-images.githubusercontent.com/58363643/195847886-6b69ca1a-c6e8-4095-8647-a66236899822.png)


      ![image](https://user-images.githubusercontent.com/58363643/195847006-a29f1486-b38c-4018-80a0-412acd26588a.png)



 
 