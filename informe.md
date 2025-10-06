# Informe Práctica No.1 — Comandos de Linux

**Autor:** Miguel Zuñiga 
**Fecha:** 05/10/2025 
**Materia:** Tendencias Tecnológicas 

---

## 🧠 Objetivo

Aprender a utilizar los comandos básicos de Linux para la creación, manipulación y eliminación de archivos y carpetas desde la terminal, comprendiendo cómo se estructuran los directorios y cómo realizar operaciones comunes con redirecciones y tuberías.

---

## 🧩 Herramientas utilizadas

- **Sistema operativo:** Git Bash 
- **Editor de texto:** Nano / Echo / Redirección 
- **Comandos principales:** `mkdir`, `cd`, `touch`, `echo`, `cat`, `cp`, `mv`, `rm`, `rmdir`, `history` 

---

## ⚙️ Procedimiento

### 1️⃣ Creación de estructura de carpetas

En el directorio de trabajo se creó una carpeta principal llamada **proyecto_comandos** y dentro de ella tres subcarpetas: **documentos**, **imagenes** y **scripts**.

```bash
mkdir proyecto_comandos
cd proyecto_comandos
mkdir documentos imagenes scripts
ls
```

**Explicación:** 
- `mkdir` crea una nueva carpeta. 
- `cd` permite ingresar a una carpeta. 
- `ls` lista el contenido del directorio actual.

**Resultado esperado:**
```
documentos  imagenes  scripts
```

---

### 2️⃣ Creación y edición de archivos

Dentro de la carpeta `documentos` se creó un archivo de texto llamado `notas.txt` y se agregaron tres líneas de texto utilizando redirección.

```bash
cd documentos
touch notas.txt
echo "Linea 1" > notas.txt
echo "Linea 2" >> notas.txt
echo "Linea 3" >> notas.txt
cat notas.txt
```

**Explicación:** 
- `touch` crea un archivo vacío. 
- `echo` imprime texto en la terminal. 
- `>` crea o sobrescribe un archivo con el texto indicado. 
- `>>` agrega texto sin borrar el contenido anterior.
- `cat` muestra el contenido del archivo.

**Resultado esperado:**
```
Linea 1
Linea 2
Linea 3
```

---

### 3️⃣ Copiar y mover archivos

El archivo `notas.txt` fue copiado a la carpeta `scripts` con el nombre `backup_notas.txt` y luego movido a la carpeta `imagenes`.

```bash
cp notas.txt ../scripts/backup_notas.txt
mv ../scripts/backup_notas.txt ../imagenes/
ls ../imagenes
```

**Explicación:**  
- `cp` copia archivos de un lugar a otro.  
- `mv` mueve o renombra archivos.  
- `..` significa “subir un nivel” en la estructura de carpetas.  
- `ls` permite verificar que el archivo se encuentre en la carpeta destino.

**Resultado esperado:**
```
backup_notas.txt
```

---

### 4️⃣ Redirección y concatenación

Se creó un nuevo archivo `resumen.txt` en la carpeta `documentos`, se redirigió el contenido de `notas.txt` a este archivo, y se añadió una nueva línea sin sobrescribir su contenido.

```bash
touch resumen.txt
cat notas.txt > resumen.txt
echo "Linea de texto sin sobrescribir lo otro" >> resumen.txt
cat resumen.txt
```

**Explicación:**  
- `touch` crea un archivo vacío.  
- `cat notas.txt > resumen.txt` copia el contenido de `notas.txt` a `resumen.txt`.  
- `echo ... >> resumen.txt` agrega texto al final del archivo.  
- `cat` permite verificar el contenido.

**Resultado esperado:**
```
Linea 1
Linea 2
Linea 3
Linea de texto sin sobrescribir lo otro
```

---

### 5️⃣ Eliminación de archivos y carpetas

Se eliminó el archivo `backup_notas.txt` de la carpeta `imagenes` y luego se eliminó la carpeta (ya vacía).

```bash
rm ../imagenes/backup_notas.txt
rmdir ../imagenes
ls ..
```

**Explicación:**  
- `rm` elimina archivos.  
- `rmdir` elimina carpetas vacías.  
- `ls ..` lista las carpetas del directorio superior.

**Resultado esperado:**
```
documentos  scripts
```

---

### 6️⃣ Guardar el historial de comandos

Se guardaron los últimos comandos ejecutados en un archivo llamado `tarea-s1-miguel_zuniga.txt` dentro de la carpeta principal.

```bash
cd ..
history | tail -n 30 > tarea-s1-miguel_zuniga.txt
```

**Explicación:**  
- `history` muestra todos los comandos usados.  
- `| tail -n 30` toma solo los últimos 30 comandos.  
- `>` redirige la salida al archivo `tarea-s1-miguel_zuniga.txt`.  
- De esta forma se conserva un registro de las acciones realizadas durante la práctica.

**Resultado esperado:**
Un archivo `.txt` con los comandos usados en la práctica.

---

## ✨ Conclusión

Esta práctica permitió afianzar el manejo básico del entorno Linux y la comprensión de sus comandos esenciales.  
Gracias al uso de redirecciones y tuberías, aprendí a combinar operaciones para crear flujos de trabajo más eficientes, reforzando la importancia de la terminal como herramienta fundamental en el ámbito del desarrollo y la administración de sistemas.






