import socket

def convert_to_celsius(fahrenheit):
    celsius = (fahrenheit - 32) * 5/9
    return celsius

def main():
    server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    server_socket.bind(('127.0.0.1', 3333))
    server_socket.listen(1)
    print("Server is ready to receive")
    connection, address = server_socket.accept()
    while True:
        fahrenheit = connection.recv(1024)
        fahrenheit = fahrenheit.decode()
        if not fahrenheit:
            break
        celsius = convert_to_celsius(float(fahrenheit))
        connection.send(str(celsius).encode())
    connection.close()
    server_socket.close()

if __name__ == '__main__':
    main()
