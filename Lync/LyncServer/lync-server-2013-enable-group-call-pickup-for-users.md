---
title: Habilitar la respuesta de llamadas en grupo para los usuarios
TOCTitle: Habilitar la respuesta de llamadas en grupo para los usuarios
ms:assetid: 20ec5f41-6ba2-4156-82ed-b91d05b62a6d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945620(v=OCS.15)
ms:contentKeyID: 52061608
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Habilitar la respuesta de llamadas en grupo para los usuarios

 

_**Última modificación del tema:** 2013-01-30_

Use las herramientas del kit de recursos de SEFAUtil para habilitar la atención de llamadas grupales para los usuarios. Para ello, se les debe asignar un número de grupo con el tipo GroupPickup en la tabla de órbitas de estacionamiento de llamadas. La asignación del número del grupo de atención de llamadas y la habilitación de la atención de llamadas grupales se llevan a cabo al mismo tiempo al usar el parámetro /enablegrouppickup cuando se ejecuta SEFAUtil.exe.

## Para habilitar la atención de llamadas grupales para un usuario

1.  Inicie sesión en el equipo en el que instaló la herramienta SEFAUtil con derechos de administrador.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por ejemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## Vea también

#### Tareas

[Asigar números de respuesta de llamadas en grupo a los usuarios](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Deshabilitar la respuesta de llamadas en grupo para los usuarios](lync-server-2013-disable-group-call-pickup-for-users.md)

