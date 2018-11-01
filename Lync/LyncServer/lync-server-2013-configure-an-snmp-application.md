---
title: Configuración de una aplicación SNMP en Lync Server 2013
TOCTitle: Configuración de una aplicación SNMP en Lync Server 2013
ms:assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412972(v=OCS.15)
ms:contentKeyID: 48276604
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de una aplicación SNMP en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-03_

Lync Server 2013 incluye una interfaz de servicio web estándar que puede usar para conectar el Servicio de información de ubicaciones a las aplicaciones del Protocolo simple de administración de redes (SNMP) que corresponden a las direcciones MAC con la información de conmutadores y puertos.

Si hay una aplicación SNMP instalada y Servicio de información de ubicaciones no encuentra una coincidencia en la base de datos de ubicaciones, Servicio de información de ubicaciones consultará automáticamente la aplicación por medio de la dirección MAC que proporciona el cliente. Servicio de información de ubicaciones usará la información de conmutadores y puertos que devuelve la aplicación SNMP para consultar de nuevo la base de datos de ubicaciones.

Para más información, consulte [Set-CsWebServiceConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsWebServiceConfiguration).


> [!NOTE]
> Las direcciones MAC no están disponibles en los equipos donde se ejecuta Windows 8.



## Para configurar la dirección URL de la aplicación SNMP:

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  Ejecute el cmdlet siguiente para configurar la dirección URL para la aplicación SNMP.
    
        Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>"

