---
title: Prueba de las opciones de configuración de troncos SIP en Lync Server 2013
TOCTitle: Prueba de las opciones de configuración de troncos SIP en Lync Server 2013
ms:assetid: c8712308-0e2d-4e39-8f90-d1a250487a94
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721880(v=OCS.15)
ms:contentKeyID: 49889678
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prueba de las opciones de configuración de troncos SIP en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-01_

Los valores de configuración de tronco SIP definen la relación y las capacidades entre un servidor de mediación y la puerta de enlace de la Red telefónica conmutada (RTC), una central de conmutación pública de IP (PBX) o un controlador de borde de sesión (SBC) en el proveedor de servicios. Estos valores determinan lo siguiente:

  - Si se debe habilitar el desvío de medios en los troncos.

  - Las condiciones en las que se envían los paquetes de protocolo de control de transporte en tiempo real (RTCP).

  - Si se requiere o no el cifrado del protocolo de tiempo real seguro (SRTP) en cada tronco.

Cuando se instala Microsoft Lync Server 2013, se crea de forma predeterminada una colección global y única de valores de configuración de tronco SIP. Los administradores también pueden crear colecciones de valores personalizadas en el ámbito del sitio o servicio (solo para el servicio de puerta de enlace de RTC). Los administradores pueden usar también el cmdlet Test-CsTrunkConfiguration para comprobar que el tronco puede convertir un número que ha marcado el usuario en un número que la puerta de enlace puede controlar.

Los valores de configuración de tronco solo se pueden probar con Windows PowerShell y el cmdlet [Test-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsTrunkConfiguration). Ejecute este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Probar los valores de configuración de tronco

  - Este comando comprueba que los valores de configuración de tronco del sitio de Redmond pueden convertir correctamente el número marcado 4255551212.
    
        $trunk = Get-CsTrunkConfiguration -Identity "site:Redmond"
        Test-CsTrunkConfiguration -DialedNumber 4255551212 -TrunkConfiguration $trunk

