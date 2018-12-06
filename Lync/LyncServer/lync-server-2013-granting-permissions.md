---
title: 'Lync Server 2013: Conceder permisos'
TOCTitle: Conceder permisos
ms:assetid: d1c9ea66-bd07-480e-99a0-011108f97e42
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398901(v=OCS.15)
ms:contentKeyID: 48276763
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conceder permisos en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-15_

Para la instalación, puede conceder permisos al grupo universal RTCUniversalServerAdmins para una unidad organizativa (OU) de Active Directory específica, lo que permite a los miembros del grupo RTCUniversalServerAdmins de dicha OU instalar Lync Server 2013 en el dominio especificado. Cuando se conceden permisos para una unidad organizativa, se conceden los siguientes permisos:

  - Lectura

  - Escritura

  - ReadSPN

  - WriteSPN

Para la administración, puede agregar permisos a las OU especificadas, de modo que los miembros de los grupos universales RTC que se han creado durante la preparación del bosque pueden obtener acceso a las OU sin ser miembros del grupo de administradores de dominio. Los permisos agregados a la OU especificada son los mismos permisos que los que el cmdlet **Enable-CsAdDomain** agrega a los equipos y los contenedores de OU de los usuarios.

## En esta sección

  - [Concesión de permisos de instalación en Lync Server 2013](lync-server-2013-granting-setup-permissions.md)

  - [Conceder permisos de unidad organizativa en Lync Server 2013](lync-server-2013-granting-organizational-unit-permissions.md)

