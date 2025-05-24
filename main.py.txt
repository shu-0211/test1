class Server:
    def __init__(self):
        self.database = []

    def receive_message(self, sender, receiver, message):
        self.database.append((sender, receiver, message))
        print(f"Server: Message stored from {sender} to {receiver}")
        self.push_notification(receiver)

    def push_notification(self, receiver):
        print(f"Server: Notification sent to {receiver}")


class App:
    def __init__(self, username, server):
        self.username = username
        self.server = server

    def send_message(self, receiver, message):
        print(f"{self.username}: Sending message to {receiver}")
        self.server.receive_message(self.username, receiver, message)


# 사용 예시
server = Server()
user1_app = App("User1", server)
user2_app = App("User2", server)

user1_app.send_message("User2", "안녕, 뭐해?")
