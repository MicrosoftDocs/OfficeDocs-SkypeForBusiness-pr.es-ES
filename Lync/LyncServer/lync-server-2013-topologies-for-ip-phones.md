---
title: Topologías para teléfonos IP
TOCTitle: Topologías para teléfonos IP
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48274719
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologías para teléfonos IP

 

_**Última modificación del tema:** 2012-06-21_

En este tema, se describe el proceso de conectividad y se explican las diferencias de la conexión de un teléfono IP en una red interna y en una red externa.


> [!NOTE]
> Lync Server admite los siguientes teléfonos IP: teléfono de área común Aastra 6721ip, teléfono de escritorio Aastra 6725ip, teléfono IP HP 4110 (teléfono de área común), teléfono IP HP 4120 (teléfono de escritorio), teléfono de escritorio IP Polycom CX600, teléfono de escritorio IP Polycom CX700, teléfono de área común IP Polycom CX500 y teléfono de conferencia IP Polycom CX3000. De estos teléfonos, todos excepto el Polycom CX700 pueden ejecutar Lync Phone Edition.



En el diagrama siguiente, se describen todos los componentes utilizados en la conectividad del dispositivo dentro del entorno corporativo.

**Topología interna**

![Dispositivos dentro de la red](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "Dispositivos dentro de la red")


> [!NOTE]
> La figura anterior constituye una representación lógica, no una descripción física. Por ejemplo, generalmente los Servicios de dominio de Active Directory (AD DS) no se encuentran en el mismo equipo que los componentes de Lync Server. El almacén de usuarios puede estar en el servidor back-end, o en los servidores de archivado o de supervisión. El Shell de administración de Lync Server, el servidor web y los servicios de actualización forman parte del rol de servidor front-end.



En el diagrama siguiente, se muestran los componentes utilizados cuando el dispositivo se encuentra fuera de la red corporativa.

**Topología externa**

![Dispositivos fuera de la red](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "Dispositivos fuera de la red")


> [!NOTE]
> El servicio web de actualización de dispositivos proporciona un sitio web externo e interno, pero aquí solo se muestra uno externo.<BR>La ubicación del registrador y la dirección URL del servicio web de actualización de dispositivos para la organización deben publicarse en DNS si se habilitará el acceso externo. Además, el servidor perimetral se debe implementar y configurar correctamente para permitir las comunicaciones externas del dispositivo al entorno corporativo, y viceversa. Esto se omite en el diagrama anterior porque la implementación perimetral no es específica de la conectividad del dispositivo.


