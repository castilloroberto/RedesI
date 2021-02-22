# Redes I 

## Actualizar switch

### Nombre del archivo de actualizacion version 15 del sistema operativo
> c2960-lanbasek9-mz.150-2.SE4.bin

## Tener en cuenta
1. deben establecer una IP para el servidor 

## Verificar version
```cli
Switch> show version
```


## Habilitar la VLAN1 del Switch

Niveles de acceso requeridos

```cli
Switch> enable
Switch# configure terminal
```

Establecer una IP y encender la interfaz

```cli
Switch(config)# interface vlan1
Switch(config-if)# ip address "cualquier ip valida" "una marcara de red para la ip"
Switch(config-if)# ip address 192.168.0.40 255.255.255.0
Switch(config-if)# no shutdown
```
### Espesificar version y fuente de la actualizacion

Desde el modo **enable**

```cli
Switch# copy tftp: flash:
```

Aqui se ingresa la direccion IP del servidor

```cli
Address or name of remote host []?
``` 

Aqui indicamos el nombre del archivo de actualizacion tal como se encuentra en el servidor
```cli
Source filename []?
``` 

En respuesta a este mensaje damos enter
```cli
Destination filename [c2960-lanbasek9-mz.150-2.SE4.bin]?
``` 

## Establecer el archivo para el arraque del sistema

```cli
Switch(config)# boot system "nombre del archivo de actualizacion"

Switch(config)# boot system c2960-lanbasek9-mz.150-2.SE4.bin
```

Guardamos los cambios

* **write** o **wr** para guardar cambios 

```cli
Switch(config)# do write
```

## Reiniciar Switch
Desde modo **enable**
```cli
Switch# reload
```
## Al Reiniciar el Switch Veridicamos la version del sistema operativo
```cli
Switch> show version
```



 
