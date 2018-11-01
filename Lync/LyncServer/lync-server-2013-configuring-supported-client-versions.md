---
title: Configuración de versiones de cliente admitidas
TOCTitle: Configuración de versiones de cliente admitidas
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48276360
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de versiones de cliente admitidas

 

_**Última modificación del tema:** 2012-12-14_

En Lync Server 2013, puede configurar directivas de versión de cliente para especificar las versiones de clientes admitidos en el entorno. Además, puede usar la configuración de versión de cliente global para especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión y que, por lo tanto, no estén explícitamente admitidos o restringidos.

También puede usar directivas de versión de cliente para administrar las actualizaciones de cliente. Cuando establece una directiva de versión de cliente y usa las opciones **Permitir y actualizar** y **Bloquear y actualizar**, los clientes recibirán software actualizado de Windows Server Update Services (si usa este servicio) o de Microsoft Update.

## Configuración de la directiva de versión de cliente

La directiva de versión de cliente predeterminada requiere que todos los clientes ejecuten Lync o Microsoft Office Communicator 2007 R2. Si los clientes del entorno ejecutan versiones anteriores de Communicator, probablemente tenga que reconfigurar las reglas de versión de cliente para impedir que los clientes y los dispositivos se bloqueen o se actualicen inesperadamente al conectarse a Lync Server 2013. Puede modificar la regla predeterminada o agregar una regla más alta en la lista de directivas de versiones de cliente para anular la regla predeterminada. Además, a medida que se publiquen actualizaciones acumulativas, deberá configurar la directiva de versión de cliente para pedir las últimas actualizaciones.

