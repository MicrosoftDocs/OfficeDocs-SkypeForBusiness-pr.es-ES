---
title: Asigar números de respuesta de llamadas en grupo a los usuarios
TOCTitle: Asigar números de respuesta de llamadas en grupo a los usuarios
ms:assetid: b8e79275-8e7e-4799-b908-f34f61df22f0
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945647(v=OCS.15)
ms:contentKeyID: 52061720
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asigar números de respuesta de llamadas en grupo a los usuarios

 

_**Última modificación del tema:** 2013-01-30_

Tras agregar números de grupo de atención de llamadas grupales a la tabla de órbita de estacionamiento de llamadas, puede asignar los grupos a usuarios. Use la herramienta de kit de recursos de activación de característica de extensión secundaria (SEFAUtil) para asignar grupos de atención de llamadas a usuarios.


> [!NOTE]
> En un entorno híbrido, no asigne un grupo de atención de llamadas grupales a los usuarios que se hospeden en línea. Este tipo de usuarios no puede participar en grupos de atención de llamadas grupales; es decir, sus llamadas no pueden ser atendidas por otros usuarios, ni tampoco pueden responder a llamadas de otros usuarios.



## Para asignar un grupo de atención de llamadas grupales a un usuario

1.  Inicie sesión como administrador en el equipo en el que haya instalado la herramienta SEFAUtil.

2.  En la línea de comandos, ejecute:
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    Por ejemplo:
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199

## Vea también

#### Tareas

[Habilitar la respuesta de llamadas en grupo para los usuarios](lync-server-2013-enable-group-call-pickup-for-users.md)  
[Deshabilitar la respuesta de llamadas en grupo para los usuarios](lync-server-2013-disable-group-call-pickup-for-users.md)

