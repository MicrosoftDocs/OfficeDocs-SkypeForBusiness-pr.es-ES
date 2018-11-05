---
title: "Habilitar la respuesta de llamadas en grupo para usuarios y asignar número de grupo"
TOCTitle: "Activer la prise d’appel de gr. pour des ut. et assigner un numéro de groupe"
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945650(v=OCS.15)
ms:contentKeyID: 52061735
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar la respuesta de llamadas en grupo para los usuarios y asignar un número de grupo

 

_**Última modificación del tema:** 2013-01-30_

Tras agregar números de grupo de atención de llamadas a la tabla de órbita de estacionamiento de llamadas, dichos números se asignan a usuarios, para los que se habilita la atención de llamadas grupales. Use la herramienta de kit de recursos de activación de característica de extensión secundaria (SEFAUtil) para asignar números de grupo y habilitar la atención de llamadas grupales.


> [!NOTE]
> En un entorno híbrido, no asigne un grupo de atención de llamadas grupales a los usuarios que se hospeden en línea. Este tipo de usuarios no puede participar en grupos de atención de llamadas grupales; es decir, sus llamadas no pueden ser atendidas por otros usuarios, ni tampoco pueden responder a llamadas de otros usuarios.



## Para asignar un número de grupo y habilitar la atención de llamadas grupales para un usuario

1.  Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por ejemplo, para asignar el número de grupo 199 a un usuario:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

## Vea también

#### Tareas

[Deshabilitar la respuesta de llamadas en grupo para los usuarios](lync-server-2013-disable-group-call-pickup-for-users.md)

