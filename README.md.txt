# 개인 실습 과제 1: 일상 속 소프트웨어 사용 사례

## 📌 주제
카카오톡과 같은 메신저에서 메시지를 보내고 받는 과정을 시퀀스 다이어그램과 코드로 구현

## 🧩 시퀀스 다이어그램
Mermaid 시퀀스 다이어그램:
```mermaid
sequenceDiagram
    participant User
    participant App
    participant Server
    participant Receiver

    User->>App: Launch app
    User->>App: Type message
    User->>App: Press send
    App->>Server: Send message data
    Server->>Server: Store message in DB
    Server->>Receiver: Push notification
    Receiver->>App: Open app and view message
