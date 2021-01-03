# socket-programming
import socket

s = socket.socket()
print("socket created")

s.bind(("localhost", 9999))

s.listen(3)
print("Waiting for the connections")

while True:
    c, addr = s.accept()
    name = c.recv(1024).decode()
    print("connected with", addr, name)
    c.send(bytes("welcome", "utf-8"))

    c.close()
    
    
    # for client
    
    import socket

c = socket.socket()

c.connect(("localhost", 9999))

name = input("Enter your name")
c.send(bytes(name,'utf-8'))

print(c.recv(1024).decode())


