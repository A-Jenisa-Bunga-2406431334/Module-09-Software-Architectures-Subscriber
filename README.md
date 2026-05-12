# Subscriber - Module 9 Event-Driven Architecture

## Understanding Subscriber and Message Broker

### a. What is amqp?
AMQP (Advanced Message Queuing Protocol) adalah protokol komunikasi jaringan yang digunakan untuk message-oriented middleware. AMQP memungkinkan aplikasi yang berbeda untuk berkomunikasi satu sama lain dengan cara mengirimkan pesan melalui message broker seperti RabbitMQ. Protokol ini menjamin pengiriman pesan, mengatur antrian pesan, dan mendukung berbagai pola komunikasi seperti publish/subscribe dan point-to-point.

### b. What does it mean? guest:guest@localhost:5672, what is the first guest, and what is the second guest, and what is localhost:5672 for?
- **guest pertama** adalah username untuk autentikasi ke RabbitMQ broker. Dalam hal ini, "guest" adalah username default yang disediakan oleh RabbitMQ.
- **guest kedua** adalah password untuk autentikasi ke RabbitMQ broker. "guest" juga merupakan password default RabbitMQ.
- **localhost:5672** menunjukkan alamat dan port dari RabbitMQ broker yang sedang berjalan. `localhost` berarti broker berjalan di komputer yang sama, dan `5672` adalah port default yang digunakan oleh protokol AMQP untuk koneksi.

## Simulation Slow Subscriber

Dengan menambahkan `thread::sleep(ten_millis)` pada subscriber, subscriber menjadi lambat dalam memproses pesan. Ketika publisher mengirim banyak pesan sekaligus, pesan-pesan tersebut menumpuk di queue RabbitMQ karena subscriber tidak dapat memprosesnya dengan cepat. Terlihat pada chart Queued messages yang naik hingga ~50 pesan, menunjukkan antrian yang belum diproses.

![Slow Subscriber](../screenshoots/slow_subscriber.png)