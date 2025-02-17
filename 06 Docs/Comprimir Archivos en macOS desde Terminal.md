
Esta guía te enseña a comprimir archivos o carpetas en macOS desde la terminal y protegerlos con una contraseña.

---

## **Requisitos Previos**
1. macOS instalado en tu computadora.
2. Acceso a la Terminal.

---

## **Pasos para Comprimir y Proteger Archivos**

### **1. Abrir la Terminal**
- Puedes abrir la Terminal desde:
  - `Finder > Aplicaciones > Utilidades > Terminal`, o
  - Usando Spotlight: `Cmd + Espacio`, escribir "Terminal" y presionar Enter.

### **2. Navegar a la Ubicación del Archivo o Carpeta**
- Usa el comando `cd` para moverte a la carpeta que contiene los archivos o carpetas que deseas comprimir.
  ```bash
  cd /ruta/a/tu/carpeta
  ```
  Ejemplo:
  ```bash
  cd ~/Documentos/Proyectos
  ```

### **3. Comprimir Archivos**
- Usa el comando `zip` para crear un archivo comprimido protegido con contraseña.

#### **Sintaxis del Comando**
```bash
zip -e nombre_del_archivo.zip archivo1 archivo2
```

#### **Opciones Explicadas**
- `-e`: Habilita la protección con contraseña.
- `nombre_del_archivo.zip`: Es el nombre del archivo comprimido que se creará.
- `archivo1 archivo2`: Lista de archivos o carpetas que deseas comprimir.

#### **Ejemplo**
Si deseas comprimir un archivo llamado `informe.pdf` y protegerlo con una contraseña:
```bash
zip -e informe_protegido.zip informe.pdf
```

Al ejecutar este comando, se te pedirá que ingreses una contraseña:
```
Enter password:
Verify password:
```
- Escribe la contraseña y verifica.
- El archivo `informe_protegido.zip` se creará en la misma ubicación.

### **4. Comprimir una Carpeta Completa**
Si deseas comprimir una carpeta completa, usa la opción `-r` para incluir todos los archivos y subcarpetas.

#### **Sintaxis del Comando**
```bash
zip -er nombre_del_archivo.zip carpeta
```

#### **Ejemplo**
Para comprimir una carpeta llamada `Proyecto`:
```bash
zip -er proyecto_protegido.zip Proyecto
```

---

## **Notas Importantes**
1. **Recuerda la contraseña**: No hay forma de recuperar la contraseña si la olvidas.
2. **Compatibilidad**: Los archivos ZIP protegidos con contraseña creados con este método son compatibles con la mayoría de los sistemas operativos.
3. **Descomprimir el Archivo**:
   - Al descomprimir (`unzip nombre_del_archivo.zip`), se te pedirá la contraseña.

---

## **Recursos Adicionales**
- [Documentación de zip](https://linux.die.net/man/1/zip)
