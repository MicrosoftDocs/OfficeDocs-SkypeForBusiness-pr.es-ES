---
title: Configurar la base de datos de ubicaciones en Lync Server 2013
TOCTitle: Configurar la base de datos de ubicaciones en Lync Server 2013
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48275897
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la base de datos de ubicaciones en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-17_

Para habilitar clientes de modo que detecten automáticamente su ubicación dentro de una red, primero tiene que configurar la base de datos de ubicaciones. Si no configura ninguna base de datos de ubicaciones, y **Ubicación obligatoria** se ha establecido como **Sí** o **Declinación de responsabilidades** en la directiva de ubicación, se le pedirá al usuario que introduzca manualmente una ubicación.

Para configurar la base de datos de ubicaciones, deberá realizar las siguientes tareas:

1.  Llene la base de datos con una búsqueda de elementos de red a las ubicaciones. Si usa una puerta de enlace de número de identificación para la ubicación de emergencia (ELIN) deberá incluir el ELIN en el \<NombredeCompañía\>.

2.  Validar las direcciones comparándolas con la Guía de calles maestra (MSAG) mantenida por el proveedor de servicios E9-1-1.

3.  Publicar la base de datos actualizada.


> [!NOTE]
> También puede optar por definir una base de datos secundaria de origen de ubicaciones, para usarla en lugar de la base de datos de ubicaciones. Para obtener información detallada, consulte <A href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurar un servicio de información de ubicación secundario en Lync Server 2013</A>.



## En esta sección

  - [Rellenar la base de datos de ubicación](lync-server-2013-populate-the-location-database.md)

  - [Validar direcciones](lync-server-2013-validate-addresses.md)

  - [Publicar la base de datos de ubicación desde Lync Server 2013](lync-server-2013-publish-the-location-database.md)

