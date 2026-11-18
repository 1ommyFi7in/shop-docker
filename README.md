# Запуск магазина в Docker

Передай стенд коллеге вместе с инструкцией, как пересоздать контейнеры и сохранить остатки.

**Этап 07** · Docker · Compose · PostgreSQL

[Этап 07](https://github.com/1ommyFi7in/java-backend-roadmap/blob/main/%D0%9E%D0%B2%D0%B5%D1%80%D0%B2%D1%8C%D1%8E.md#07-docker-%D0%B8-kubernetes) · [Техническое задание](SPECIFICATION.md) · [Тестовые данные](https://github.com/1ommyFi7in/java-backend-roadmap/blob/main/%D0%9F%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D1%8B/%D0%9A%D0%BE%D0%BD%D1%82%D1%80%D0%B0%D0%BA%D1%82%D1%8B%20%D0%B8%20%D1%82%D0%B5%D1%81%D1%82%D0%BE%D0%B2%D1%8B%D0%B5%20%D0%B4%D0%B0%D0%BD%D0%BD%D1%8B%D0%B5%20%D0%BC%D0%B0%D0%B3%D0%B0%D0%B7%D0%B8%D0%BD%D0%B0.md) · [Весь маршрут](https://github.com/1ommyFi7in/java-backend-roadmap)

> [!NOTE]
> Учебное задание. В репозитории находятся постановка, примеры и критерии приёмки. Реализацию добавляй по мере прохождения этапа.

## Результат этапа

| Что собрать | Что отработать |
| --- | --- |
| Dockerfile, Compose, шаблон окружения и два прогона с разными томами. | Image, DNS, readiness, именованные тома, Kubernetes как дополнительная лабораторная. |

## Как выглядит результат

```sh
docker compose up -d --wait db
docker compose run --rm catalog show 11 --via jdbc
```

```text
11 SKU-11 Кружка 49.90 stock=3
```

Если через CLI разместить заказ на две единицы, перезапустить стенд без удаления тома и повторить команду, ответ заканчивается на `stock=1`.

## Проверка перед сдачей

- [ ] Собрать образ и запустить чистый стенд по README. Показать чтение каталога, сохранение изменённого остатка и рабочий повторный запуск.

## Начать работу

```sh
git clone https://github.com/1ommyFi7in/shop-docker.git
cd shop-docker
```

Открой [техническое задание](SPECIFICATION.md), подготовь входные данные и начни с основного сценария. Команды запуска и проверок добавь после первого рабочего прогона.

[← Конкурентный резерв и диагностика JVM](https://github.com/1ommyFi7in/shop-concurrency-jvm) · [Магазин на JDBC и HTTP →](https://github.com/1ommyFi7in/shop-jdbc-servlets)
