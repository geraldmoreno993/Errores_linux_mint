# Linux no detecta directamente tarjeta SD de cámara fotográfica

## 1.- Verifica la conexión física: Asegúrate de que la tarjeta SD esté bien insertada y que el lector de tarjetas de tu laptop funcione correctamente.

## 2.- En versiones más recientes de Linux Mint, como Linux Mint 21 (Victoria) 
El paquete exfat-utils ha sido reemplazado por el paquete exfatprogs. Para solucionar el problema de la tarjeta SD con formato exFAT, sigue estos pasos:
Instala exfat-fuse y exfatprogs: Estos son los paquetes actualizados para manejar sistemas de archivos exFAT:
```
sudo apt install exfat-fuse exfatprogs
```

## 3.- Verifica si la tarjeta SD es detectada: Después de la instalación, vuelve a conectar la tarjeta SD y verifica si el sistema la detecta automáticamente. Si no es así, puedes intentar montarla manualmente:
```
sudo mount -t exfat /dev/sdX1 /mnt/sdcard
```

# 4.- Montar la tarjeta SD: Una vez que hayas identificado el dispositivo correcto (por ejemplo, /dev/sdb1 o /dev/mmcblk0p1), usa ese nombre en lugar de /dev/sdX1 para montar la tarjeta:
```
sudo mount -t exfat /dev/sdXX /mnt/sdcard
```

# 5.- Identificar el nombre del dispositivo de la tarjeta SD
Ejecuta el siguiente comando para listar los dispositivos de almacenamiento conectados a tu sistema:
```
lsblk
```

# 6.- Verificar el dispositivo detectado
Si no está claro cuál es tu tarjeta SD, puedes volver a ejecutar el siguiente comando para ver los últimos eventos registrados por el kernel después de haber insertado la tarjeta SD:
```
sudo dmesg | tail

```
