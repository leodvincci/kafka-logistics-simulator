# Kafka Logistics Simulator<img width="1536" height="1024" alt="ChatGPT Image Nov 27, 2025, 05_14_55 AM" src="https://github.com/user-attachments/assets/a54dfbfe-419b-48a4-bea6-8df037c9a416" />





### 🚛 Making Kafka Messy (On Purpose)



I built this **Spring Boot simulator** because I realized something while learning Kafka: sending simple strings like "Hello World" doesn't teach you how to handle the real world.

To truly understand stream processing, I needed data that was messy, realistic, and complex. This project acts as a **virtual logistics carrier**, generating a full lifecycle of shipment events—departures, GPS pings, delays, and deliveries—and streaming them right into my Kafka producer.

It’s the chaos engine that powers my learning.

------



## Why I Built This



Building a producer and a consumer is a great start, but it’s only half the battle. I wanted to see what happens when:

- Events arrive out of order.
- Timestamps conflict.
- A truck gets "delayed" in the middle of a stream.

This simulator bridges the gap between theory and reality. It provides the **movement** and state transitions needed to actually stress-test the logic in my other repos:

- **kafka-producer-hello-world** — The entry point.
- **kafka-consumer-hello-world** — The logic handler.
- **kafka-logistics-simulator** — The heartbeat where the data comes alive.

------



## What’s Under the Hood?



I designed this to mimic a real logistics network. It generates JSON payloads for events like:

- `SHIPMENT_CREATED` & `PICKED_UP`
- `DEPARTED_ORIGIN` & `LOCATION_PING` (with timestamps)
- `SHIPMENT_DELAY` (to test exception handling)
- `OUT_FOR_DELIVERY` & `DELIVERED`

Everything is timestamped, formatted as JSON, and ready to be thrown into a topic.

------



## How I Use It



This is my personal playground for:

- Testing partition strategies and message keys.
- Experimenting with event-sourced state machines.

------



## What’s Next?



I’m constantly adding features to make the simulation harder to crack:

- [ ] Randomized routing logic
- [ ] Parallel shipment streams (high volume)
- [ ] A CLI trigger mode
- [ ] "Continuous Traffic Mode" via Cron
