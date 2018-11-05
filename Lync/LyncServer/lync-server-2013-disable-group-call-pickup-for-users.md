---
title: Deshabilitar la respuesta de llamadas en grupo para los usuarios
TOCTitle: Deshabilitar la respuesta de llamadas en grupo para los usuarios
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945638(v=OCS.15)
ms:contentKeyID: 52061678
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Deshabilitar la respuesta de llamadas en grupo para los usuarios

 

_**Última modificación del tema:** 2013-01-30_

Haga lo siguiente para deshabilitar la respuesta de llamadas en grupo para un usuario.


> [!NOTE]
> Cuando se deshabilita la respuesta de llamadas en grupo para un usuario, no se conserva el número de respuesta de llamadas en grupo que se asignó al usuario. Si posteriormente quiere volver a habilitar la respuesta de llamadas en grupo para ese usuario, tendrá que volver a asignar el número de respuesta de llamadas en grupo con el parámetro /enablegrouppickup.



## Para deshabilitar la respuesta de llamadas en grupo para un usuario

1.  Inicie sesión como administrador en el equipo en el que instaló la herramienta SEFAUtil.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    Por ejemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

## Vea también

#### Tareas

[Asigar números de respuesta de llamadas en grupo a los usuarios](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[Habilitar la respuesta de llamadas en grupo para los usuarios](lync-server-2013-enable-group-call-pickup-for-users.md)

