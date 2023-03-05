# Домашнее задание к занятию 10.6 «Disaster recovery» - Серебряков Руслан


### Задание 1

В чём разница между DRaaS, BaaS, Active-Active, Active-Passive?

*Приведите ответ в свободной форме.*

DRaaS - это услуга восстановления после различных инцедентов/катастроф. В случае потери данных - можно быстро откатиться на момент наличия тех самых данных. Система работает постоянно.


BaaS - это услуга резервного копирования создание копий происходит в заданный промежуток времени.


Основные различия между ними в том, что DRaaS предоставляет полное восстановление системы после катастрофы, в то время как BaaS предоставляет только резервное копирование данных.


Active-Active у нас настроено несколько (например) ЦОДов которые активны и распределяют нагрузку между собой. В случае отказа одного из них - второй берёт всё на себя.


Active-Passive у нас настроено несколько (например) ЦОДов из которых 1 активен, а 1 пассивен. В случае отказа активного ЦОДа - пассивный становится активным.

Active-Active и Active-Passive являются методами развертывания ИТ-систем, которые используются для увеличения доступности и надежности системы. При этом Active-Active используется для распределения нагрузки между несколькими ЦОД, а Active-Passive - для обеспечения резервного ЦОД в случае отказа основного.

---

### Задание 2

Компании нужно составить план восстановления в случае Disaster recovery. Сервер состоит из системного диска и диска с данными. 
Требуется копировать два логических диска на один физический: 
- системный диск (C:) (20 гигабайт);
- диск с данными (D:) (256 гигабайт). 

В требованиях говорится: 
- данные критичны в течение 24 часов после аварии;
- сеть критична к большим потокам данных в рабочее время;
- рабочее время с 9.00 до 18.00, пять дней (понедельник – пятница);
- план резервирования должен быть реализован для диска C и для диска D. В случае Linux-систем /dev/sda1, /dev/sda4 или /dev/sdb1-данные;
- считается, что для этой задачи может быть: 1) поставлен второй сервер или 2) выбрана облачная инфраструктура с определённой услугой;
- компания готова платить за 10 терабайт места как в одном, так и в другом случае.
 
*Приведите ответ в форме плана востановления с выбранным механизмом и получившейся топологией.*

- Я бы предложил поставить второй пассивный сервер на который пишется бэкап (полный) основного сервера. Бэкапы писать только в часы наименьшей нагрузки (ночью)
- Так же рекомендуется хранить как минимум 1 ежедневный, 1 недельный, 1 месячный и 1 полугодовой.
В случае сбоя - переключить всех на резервный сервер, либо восстанавливать бэкапы.


---

# Задания со звёздочкой*

Эти задания дополнительные. Их выполнять не обязательно. На зачёт это не повлияет. Вы можете их выполнить, если хотите глубже разобраться в материале.
 

### Задание 3*

Используя программу R-sync, составьте конфигурацию для выполнения прошлой задачи.

*Пришлите файл конфигурации.*




