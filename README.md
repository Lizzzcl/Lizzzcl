usuarios = []

def registrar_usuario():
    nombre = input("Ingrese nombre: ")
    apellidos = input("Ingrese apellidos: ")
    telefono = input("Ingrese número de teléfono (10 dígitos): ")
    correo = input("Ingrese correo electrónico: ")

    if 5 <= len(nombre) <= 50 and 5 <= len(apellidos) <= 50 and len(telefono) == 10 and 5 <= len(correo) <= 50:
        usuario = {"id": len(usuarios) + 1, "nombre": nombre, "apellidos": apellidos, "telefono": telefono, "correo": correo}
        usuarios.append(usuario)
        print("¡Usuario registrado con éxito!")
    else:
        print("Error: Datos inválidos. Asegúrate de seguir las indicaciones.")

def imprimir_identificadores():
    print("Listado de Identificadores:")
    for usuario in usuarios:
        print(f"Usuario ID: {usuario['id']}")

print("¡Bienvenido al Registro de Usuarios!")

try:
    num_usuarios = int(input("¿Cuántos usuarios deseas registrar? "))
except ValueError:
    print("Error: Ingresa un número válido.")
    exit()

for _ in range(num_usuarios):
    print("\nIngresa los datos del usuario:")
    registrar_usuario()

imprimir_identificadores()
