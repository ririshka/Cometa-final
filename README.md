# Cometa-final

## Описание проекта

**Cometa-final** — это итоговый проект DevOps & DBA, включающий веб-приложение на Flask, развернутое в Docker-контейнерах, с автоматизированным процессом деплоя, настроенным с помощью GitHub Actions и Ansible.

## Структура проекта

```bash
Cometa-final/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── ansible/
│   ├── inventory.yml
│   └── playbook.yml
├── app/
│   ├── Dockerfile
│   ├── requirements.txt
│   └── app.py
├── db/
│   └── Dockerfile
├── docker-compose.yml
└── README.md
```

# Описание проекта

## Описание директорий и файлов

### `.github/workflows/deploy.yml`
Конфигурация GitHub Actions для автоматического деплоя приложения при пуше в ветку `main`. Этот workflow выполняет следующие шаги:
- Проверка кода из репозитория.
- Аутентификация в Docker Hub.
- Сборка и отправка Docker-образов для приложения и базы данных.
- Настройка SSH-ключа для Ansible.
- Запуск Ansible playbook для развертывания приложения на удаленном сервере.

### `ansible/`
Содержит файлы для автоматизации развертывания с помощью Ansible.
- `inventory.yml`: Определяет хосты и их параметры для деплоя.
- `playbook.yml`: Набор задач Ansible для установки Docker и запуска контейнеров с приложением и базой данных.

### `app/`
Директория с исходным кодом веб-приложения на Flask.
- `Dockerfile`: Инструкции по созданию Docker-образа для приложения.
- `requirements.txt`: Список зависимостей Python для приложения.
- `app.py`: Основной файл приложения Flask.

### `db/`
Директория с конфигурацией базы данных.
- `Dockerfile`: Инструкции по созданию Docker-образа для базы данных.

### `docker-compose.yml`
Файл для оркестрации многоконтейнерного Docker-приложения, определяющий сервисы приложения и базы данных, их образы, порты и зависимости.

### `README.md`
Текущий файл с описанием проекта, его структурой и инструкциями по развертыванию.

---

## Инструкции по развертыванию и запуску

### Предварительные требования
- Поднять EC2-instance в AWS
- Установленный [Docker](https://docs.docker.com/get-docker/).
- Установленный [Docker Compose](https://docs.docker.com/compose/install/).
- Доступ к удаленному серверу с установленным [Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) для деплоя.

---

### Локальный запуск с использованием Docker Compose

1. **Клонирование репозитория**:
   ```bash
   git clone https://github.com/ririshka/Cometa-final.git
   cd Cometa-final

## Скриншоты

### Основное изображение
![docker ps](https://github.com/ririshka/Cometa-final/blob/main/image.png)

### Дополнительное изображение 1
![HTTP](https://github.com/ririshka/Cometa-final/blob/main/image2.png)

### Дополнительное изображение 2
![CICD](https://github.com/ririshka/Cometa-final/blob/main/image3.png)
